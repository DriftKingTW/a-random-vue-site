<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/user">User</router-link>
    </div>
    <router-view />
  </div>
</template>

<style lang="scss">
@import "@/assets/master.scss";

#app {
  text-align: center;
  min-height: 100vh;
  color: $primary;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: $secondary;

    &.router-link-exact-active {
      color: $secondary-dark;
    }
  }
}
</style>
