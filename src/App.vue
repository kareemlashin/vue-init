<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </div>
  <p>{{ $t("message") }}</p>
  <button @click="changeLocale('ar')">ar</button>
  <button @click="changeLocale('en')">en</button>
  <router-view />
</template>
<script>
export default {
  methods: {
    changeLocale(locale) {
      localStorage.setItem("lang", locale);
      this.$i18n.locale = locale;
    },
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
