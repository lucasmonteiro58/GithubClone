<template>
  <div class="content">
    <div class="title">Top languages</div>
    <div class="icones">
      <div v-for="language in languages" :key="language" class="language">
        <span class="circle" :style="{ backgroundColor: color() }"></span
        >{{ language }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      languages: ['HTML', 'Java', 'JavaScript', 'CSS', 'PHP'],
    }
  },
  methods: {
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
  border: 1px solid #b4b4b44f;
  border-radius: 5px;
  padding: 16px;

  .title {
    font-size: 16px;
    padding-left: 3px;
    padding-bottom: 10px;
    font-weight: 200;
    color: black;
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
  }
}
</style>
