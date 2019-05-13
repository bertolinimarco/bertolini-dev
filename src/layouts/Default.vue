<template>
  <div id="app">
    <header class="header" v-if="showNav">
      <div class="logo">
        <Logo v-if="showLogo" aria-label="Home"/>
      </div>

      <div class="nav">
        <a href="/about">About</a>
        <a href="/blog">Blog</a>
        <a href="/projects">Projects</a>
        <ToggleTheme/>
      </div>
    </header>

    <main class="main">
      <slot/>
    </main>

  </div>
</template>

<script>
import Logo from "~/components/Logo.vue";
import ToggleTheme from "~/components/ToggleTheme.vue";

export default {
  props: {
    showLogo: { default: true },
    showNav: { default: true }
  },
  components: {
    Logo,
    ToggleTheme
  }
};
</script>

<style lang="scss">
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  min-height: var(--header-height);
  padding: 0 calc(var(--space) / 2);
  top: 0;
  z-index: 10;

  .logo,
  .nav {
    display: flex;
    align-items: center;
    a {
      margin: 0.25rem 0.75em;
      color: var(--body-color);
    }
  }

  @media screen and (min-width: 1300px) {
    position: fixed;
    width: 100%;
  }
}

.is-homepage {
  .main {
    height: 100vh;
    justify-content: center;
    align-items: center;
    display: flex;
  }
}

.main {
  margin: 0 auto;
  padding: 4.5rem 2.5rem 2.5rem 2.5rem;
  @media screen and (max-width: 650px) {
    padding: 2.5rem 0.27rem 0;
  }
}
.page-title {
  padding: calc(var(--space) / 2) 0 calc(var(--space) / 2);
  text-align: center;
}
.page-title__text {
  text-align: center;
}
</style>
