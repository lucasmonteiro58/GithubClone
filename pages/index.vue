<template>
  <div class="main-container">
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
          <li><i class="fas fa-book"></i> Repositories</li>
          <li><i class="fas fa-box"></i> Packages</li>
          <li><i class="far fa-user"></i> People</li>
          <li><i class="far fa-list-alt"></i> Projects</li>
        </ul>
      </b-row>
    </b-container>
    <b-container>Sigup container</b-container>
    <b-container class="pinned-repositories">
      pinned-repositories
      <b-row no-gutters>
        <b-col> Repositories 1</b-col>
        <b-col> Repositories 2</b-col>
        <b-col> Repositories 3</b-col>
      </b-row>
    </b-container>
    <b-container class="list-repositories">
      list-repositories
    </b-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      profile: {},
    }
  },
  created() {
    this.fetchSomething()
  },
  methods: {
    async fetchSomething() {
      const data = await this.$axios.$get(
        'https://api.github.com/users/camunda'
      )
      this.profile = data
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

  .top-container {
    margin-bottom: 16px;
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
          li {
            display: inline;
            padding-right: 10px;
          }
        }
      }
    }

    .nav-profile {
      .list-items {
        list-style: none;
        padding: 0px;
        margin: 0px;
        li {
          display: inline;
          padding: 0 16px;
        }
      }
    }
  }
}
</style>
