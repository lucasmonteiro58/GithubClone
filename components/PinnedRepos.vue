<template>
  <div class="content">
    <div class="title"><i class="fas fa-book"></i> {{ title }}</div>
    <div class="description">{{ description }}</div>
    <div class="icones">
      <div class="language"><span class="circle"></span>{{ language }}</div>
      <div class="starts"><i class="far fa-star"></i> {{ stars }}</div>
      <div class="members"><i class="fas fa-users"></i>{{ forks }}</div>
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
        'sdkf  fdsbf dfndsf dsfnsdkjfnksdnfmsdnfjnsdkfnksdbf sdf sdfdsfdfdgdffg',
    },
    language: {
      type: String,
      default: 'Java',
    },
    stars: {
      type: String,
      default: '266',
    },
    forks: {
      type: String,
      default: '222',
    },
  },
}
</script>

<style lang="scss" scoped>
.content {
  border-radius: 6px;
  border-color: rgba(0, 0, 0, 0.151);
  border-style: solid;
  border-width: 1px;
  padding: 16px;

  .title {
    font-size: 14px;
    padding-left: 3px;
    font-weight: 600;
    color: #0366d6;
    .fa-book {
      color: rgba(0, 0, 0, 0.5);
    }
  }

  .description {
    font-size: 12px;
    padding: 12px 0;
    min-height: 80px;
    text-overflow: clip;
  }

  .icones {
    display: flex;
    width: 100%;
    align-items: flex-start;
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
        background-color: yellowgreen;
      }
    }
    .members {
      .fa-users {
        margin-right: 5px;
        color: rgba(0, 0, 0, 0.596);
      }
    }
  }
}
</style>
