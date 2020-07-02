<template>
  <b-navbar toggleable="lg" type="dark" sticky class="main-navbar">
    <b-container>
      <b-navbar-brand href="#"
        ><img
          class="github-logo"
          src="~/assets/img/github-logo.png"
          alt="logo-github"
      /></b-navbar-brand>
      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav align="center">
          <b-nav-item-dropdown text="Why Github?">
            <b-dropdown-item href="#"><b>Features</b></b-dropdown-item>
            <b-dropdown-item href="#">Code review</b-dropdown-item>
            <b-dropdown-item href="#">Project management</b-dropdown-item>
            <b-dropdown-item href="#">Integrations</b-dropdown-item>
            <b-dropdown-item href="#">Actions</b-dropdown-item>
            <b-dropdown-item href="#">Packages</b-dropdown-item>
            <b-dropdown-item href="#">Security</b-dropdown-item>
            <b-dropdown-item href="#">Team management</b-dropdown-item>
            <b-dropdown-item href="#">Hosting</b-dropdown-item>
          </b-nav-item-dropdown>
          <b-nav-item href="#">Team</b-nav-item>
          <b-nav-item href="#">Enterprise</b-nav-item>
          <b-nav-item-dropdown text="Explore">
            <b-dropdown-item href="#"><b>Explore GitHub</b></b-dropdown-item>
            <b-dropdown-item href="#">Learn and contribute</b-dropdown-item>
            <b-dropdown-item href="#">Topics</b-dropdown-item>
            <b-dropdown-item href="#">Collections</b-dropdown-item>
            <b-dropdown-item href="#">Trending</b-dropdown-item>
            <b-dropdown-item href="#">Learning Lab</b-dropdown-item>
            <b-dropdown-item href="#">Open source guides</b-dropdown-item>
            <b-dropdown-item href="#">Connect with others</b-dropdown-item>
            <b-dropdown-item href="#">Events</b-dropdown-item>
            <b-dropdown-item href="#">Community forum</b-dropdown-item>
            <b-dropdown-item href="#">GitHub Education</b-dropdown-item>
          </b-nav-item-dropdown>
          <b-nav-item href="#">Marketplace</b-nav-item>
          <b-nav-item-dropdown text="Pricing">
            <b-dropdown-item href="#"><b>Plans</b></b-dropdown-item>
            <b-dropdown-item href="#">Compare plans</b-dropdown-item>
            <b-dropdown-item href="#">Contact Sales</b-dropdown-item>
            <b-dropdown-item href="#"><b>Nonprofit</b></b-dropdown-item>
            <b-dropdown-item href="#"><b>Education</b></b-dropdown-item>
          </b-nav-item-dropdown>
          <b-nav-form>
            <b-form-input
              size="sm"
              class="mr-sm-2 input-style"
              placeholder="Search"
            ></b-form-input>
          </b-nav-form>
          <b-nav-item class="no-collapse hide-c" href="#">Sing in</b-nav-item>
        </b-navbar-nav>
        <b-navbar-nav class="no-collapse hide-c" align="center">
          <b-nav-item class="is-button" href="#">Sing up</b-nav-item>
        </b-navbar-nav>
      </b-collapse>
    </b-container>
  </b-navbar>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.github-logo {
  width: 32px;
  filter: invert(1);
}

.is-button {
  border-radius: 6px;
  border-color: whitesmoke;
  border-style: solid;
  border-width: 1px;
}
.main-navbar {
  padding: 14px;
  background-color: #24282e;
  color: white;
}

.input-style {
  background-color: #40444a;
  border-radius: 6px;
  border-width: 0px;
  margin: 0 15px;
  color: white;
  min-width: 250px;
  &:focus {
    background-color: white;
    color: black;
  }
}

b-nav-item {
  color: white;
}

@media (max-width: 991.98px) {
  .no-collapse {
    display: none;
  }
}

@media (max-width: 1200px) {
  .hide-c {
    display: none;
  }
}
</style>
