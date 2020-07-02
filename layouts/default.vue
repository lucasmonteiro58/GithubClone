<template>
  <div>
    <github-header></github-header>
    <Nuxt />
    <footer><p>© 2020 GitHub, Inc.</p></footer>
  </div>
</template>
<script>
import GithubHeader from '../components/GithubHeader'
export default {
  components: { GithubHeader },
}
</script>

<style>
html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

footer {
  display: flex;
  width: 100%;
  align-items: center;
  justify-content: center;
  padding: 30px;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}
.header {
  display: flex;
  align-items: center;
  font-size: 14px;
  line-height: 1.5;
  color: hsla(0, 0%, 100%, 0.7);
  background-color: #24292e;
  padding: 16px;
}
.logo {
  filter: invert(1);
  width: 31px;
}
</style>
