<template>
  <div class="content">
    <div class="title">{{ title }}</div>
    <div class="description">{{ description }}</div>
    <div class="icones">
      <div class="language">
        <span class="circle" :style="{ backgroundColor: color }"></span
        >{{ language }}
      </div>
      <div class="licence">
        <i class="fas fa-balance-scale"></i> {{ license }}
      </div>
      <div class="forks"><i class="fas fa-users"></i>{{ forks }}</div>
      <div class="starts"><i class="far fa-star"></i> {{ stars }}</div>
      <div class="issues">
        <i class="fas fa-exclamation-circle"></i>{{ issues }}
      </div>
      <div class="update">{{ update }}</div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: 'exemplo-de titulo',
    },
    description: {
      type: String,
      default:
        'sdkf fdsbf dfndsf dsfnsdkjfnksdnfmsdnfjnsdkfnksdbf sdf sdfdsfdfdgdffg',
    },
    language: {
      type: String,
      default: 'Java',
    },
    license: {
      type: String,
      default: 'Apache',
    },
    forks: {
      type: Number,
      default: 2,
    },
    update: {
      type: String,
      default: '2 horas atrás',
    },
    stars: {
      type: Number,
      default: 5,
    },
    issues: {
      type: Number,
      default: 3,
    },
  },
  computed: {
    color() {
      const letters = '0123456789ABCDEF'
      let color = '#'
      for (let i = 0; i < 6; i++) {
        color += letters[Math.floor(Math.random() * 16)]
      }
      return color
    },
  },
}
</script>

<style lang="scss" scoped>
.content {
  border-bottom: 1px solid #b4b4b44f;
  padding: 16px;

  .title {
    font-size: 20px;
    padding-left: 3px;
    font-weight: 600;
    color: #0366d6;
    .fa-book {
      color: rgba(0, 0, 0, 0.5);
    }
  }

  .description {
    font-size: 14px;
    padding: 8px 0;
    text-overflow: clip;
  }

  .icones {
    display: flex;
    width: 100%;
    align-items: flex-start;
    flex-wrap: wrap;
    div {
      padding-right: 15px;
      font-size: 12px;
    }

    .language {
      .circle {
        position: relative;
        top: 1px;
        margin-right: 5px;
        display: inline-block;
        width: 12px;
        height: 12px;
        border-radius: 50%;
      }
    }
    .forks {
      .fa-users {
        margin-right: 5px;
        color: rgba(0, 0, 0, 0.596);
      }
    }
    .issues {
      .fa-exclamation-circle {
        margin-right: 5px;
        color: rgba(0, 0, 0, 0.596);
      }
    }
  }
}
</style>
