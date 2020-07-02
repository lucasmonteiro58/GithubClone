<template>
  <div class="main-container">
    <div class="top-container-full">
      <b-container class="top-container">
        <b-row class="profile-information" no-gutters align-content="center">
          <div class="container-photo">
            <img class="profile-photo" :src="profile.avatar_url" alt="" />
          </div>
          <div class="profile-details">
            <b-row class="profile-name" cols="12" no-gutters>{{
              profile.name
            }}</b-row>
            <b-row class="profile-list-itens" cols="12" no-gutters>
              <ul class="list-items">
                <li>
                  <i class="fas fa-map-marker-alt"></i>
                  {{ profile.location }}
                </li>
                <li>
                  <i class="fas fa-link"></i>
                  {{ profile.blog }}
                </li>
                <li>
                  <i class="far fa-envelope"></i>
                  {{ profile.email }}
                </li>
              </ul>
            </b-row>
          </div>
        </b-row>
        <b-row class="nav-profile">
          <ul class="list-items">
            <li class="active">
              <i class="fas fa-book"></i> Repositories
              <span class="circle-gray">{{ profile.public_repos }}</span>
            </li>
            <li><i class="fas fa-box"></i> Packages</li>
            <li><i class="far fa-user"></i> People</li>
            <li><i class="far fa-list-alt"></i> Projects</li>
          </ul>
        </b-row>
      </b-container>
    </div>
    <!-- <b-container>Singup container</b-container> -->
    <b-container class="pinned-repositories">
      <p class="title">Pinned Repositories</p>
      <div class="content-pined">
        <b-row no-gutters>
          <b-col
            v-for="pinned in pinnedRepositories"
            :key="pinned.index"
            md="4"
            sm="12"
            class="pinned-repos"
          >
            <pinned-repos
              :title="pinned.repo"
              :description="pinned.description"
              :language="pinned.language"
              :stars="pinned.stars"
              :forks="pinned.forks"
            ></pinned-repos>
          </b-col>
        </b-row>
      </div>
    </b-container>
    <b-container class="list-repositories">
      <b-row no-gutters>
        <b-col md="9" sm="12" class="list-repos">
          <full-repos
            v-for="repos in listRepositories"
            :key="repos.index"
            :title="repos.name"
            :description="repos.description"
            :language="repos.language"
            :forks="repos.forks"
            :stars="repos.stargazers_count"
            :issues="repos.open_issues_count"
            :update="getTime(repos.updated_at)"
          ></full-repos>
        </b-col>
        <b-col md="3" sm="12" class="top-languages">
          <top-language></top-language>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import moment from 'moment'
import PinnedRepos from '../../components/PinnedRepos'
import FullRepos from '../../components/FullRepos'
import TopLanguage from '../../components/TopLanguage'
export default {
  components: {
    PinnedRepos,
    FullRepos,
    TopLanguage,
  },
  data() {
    return {
      profile: {},
      pinnedRepositories: {},
      listRepositories: {},
      teste: [],
      // user: this.$route.params.repos,
    }
  },
  computed: {
    user() {
      if (this.$route.params.repos) {
        return this.$route.params.repos
      } else {
        return 'camunda'
      }
    },
  },
  created() {
    this.getProfile()
    this.getPinnedRepos()
    this.getListRepos()
    this.getTopLanguage()
  },
  methods: {
    async getProfile() {
      const data = await this.$axios.$get(
        'https://api.github.com/users/' + this.user
      )
      this.profile = data
    },
    async getPinnedRepos() {
      const data = await this.$axios.$get(
        'https://gh-pinned-repos.now.sh/?username=' + this.user
      )
      this.pinnedRepositories = data
    },
    async getListRepos() {
      const data = await this.$axios.$get(
        'https://api.github.com/users/' + this.user + '/repos'
      )
      this.listRepositories = data
    },
    getTime(data) {
      return moment(data).fromNow()
    },
    async getTopLanguage() {
      // const obj = await this.$axios.$get(
      //   'https://api.github.com/users/camunda/repos'
      // )
    },
  },
}
</script>

<style lang="scss" scoped>
.main-container {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;

  .top-container-full {
    width: 100%;
    border-bottom: 1px solid #b4b4b44f;
    margin-bottom: 16px;
    background-color: #fafbfd;
    .top-container {
      .profile-information {
        min-height: 130px;
        .container-photo {
          display: flex;
          justify-content: center;
          align-items: center;
          .profile-photo {
            width: 100px;
            overflow: hidden;
            vertical-align: middle;
            border-radius: 6px;
          }
        }
      }

      .profile-details {
        display: flex;
        flex-direction: column;
        justify-content: space-evenly;
        align-items: start;
        margin-left: 16px;
        .profile-name {
          font-size: 20px;
          font-weight: 400;
          min-height: 32px;
          padding-bottom: 20px;
        }
        .profile-list-itens {
          font-size: 12px;
          .list-items {
            list-style: none;
            padding: 0px;
            margin: 0px;
            display: flex;
            li {
              padding-right: 10px;
            }
          }
        }
      }

      .nav-profile {
        overflow-x: auto;
        overflow-y: hidden;
        .list-items {
          list-style: none;
          padding: 0px;
          margin: 0px;
          display: flex;
          flex-wrap: nowrap;
          li {
            display: flex;
            flex-wrap: nowrap;
            padding: 16px 16px 10px 16px;
            &:hover {
              border-bottom: 2px solid #b4b4b4;
              cursor: pointer;
            }
            &.active {
              border-bottom: 2px solid #e18879;
            }

            .circle-gray {
              border-radius: 10px;
              font-size: 11px;
              font-weight: 100;
              background-color: rgba(156, 156, 156, 0.274);
              margin: 0px 5px;
              padding: 3px;
              text-align: center;
              height: 23px;
            }
            svg {
              margin-right: 8px;
              color: rgba(0, 0, 0, 0.623);
            }
          }
        }
      }
    }
  }

  .pinned-repositories {
    border-bottom: 1px solid #b4b4b44f;
    .content-pined {
      width: 100%;
      display: flex;

      .pinned-repos {
        padding: 0 8px;
        margin-bottom: 16px;
      }
    }
  }

  .list-repositories {
    .list-repos {
      padding-right: 20px;
    }
  }
}

.top-languages {
  padding: 16px;
}

@media (max-width: 510px) {
  .top-container {
    margin-top: 16px;
  }

  .profile-list-itens {
    .list-items {
      flex-direction: column;
    }
  }
}

@media (max-width: 768px) {
  .pinned-repos {
    margin-bottom: 16px;
  }
}
</style>
