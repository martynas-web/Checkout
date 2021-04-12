<template>
  <header class="header">
  <div>
  <b-navbar class="navigation-bar px-5 py-3 mb-3" toggleable="lg" type="light">
    <b-navbar-brand href="#">
      <img src="../../assets/logo watch.svg" width="200px" height="auto" alt="watch">
    </b-navbar-brand>
    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav class="pl-5">
        <img src="../../assets/Frame.svg" width="20px" height="auto" alt="watch"><b-nav-item>Secure Checkout</b-nav-item>
      </b-navbar-nav>
      <b-navbar-nav class="ml-auto">
        <img src="../../assets/secure-logos.png" width="100%" height="auto" alt="watch">
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
  </div>
  </header>
</template>

<script>
export default {};
</script>

<style scoped>
.navigation-bar {
  background-color: white;
  box-shadow: 0 2px 5px 1px rgb(64 60 67 / 16%);
}
</style>