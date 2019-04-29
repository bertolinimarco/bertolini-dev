<template>
  <div class="author">
    <g-image
      alt="Marco Bertolini"
      class="author__image"
      src="https://pbs.twimg.com/profile_images/832656663647707140/9rNz5PXO_400x400.jpg"
      blur="5"
    />

    <h1 v-if="showTitle">Ciao, i'm Marco.</h1>

    <p
      class="author__intro"
    >I'm a Front End Developer who remembers when websites were only a bunch of tables.</p>

    <div class="author__links">
      <g-link to="/about">About</g-link>
      <g-link to="/blog">Blog</g-link>
      <g-link to="/projects">Projects</g-link>
      <a href="//twitter.com/devberto" target="_blank" rel="noopener">Twitter</a>
      <a href="//github.com/bertolinimarco/" target="_blank" rel="noopener">GitHub</a>
    </div>
    <ToggleTheme class="toggle-theme"/>
  </div>
</template>

<script>
import ToggleTheme from "~/components/ToggleTheme.vue";
export default {
  props: ["showTitle"],
  components: {
    ToggleTheme
  }
};
</script>

<style lang="scss">
.author {
  margin: 0 auto;

  text-align: center;
  padding: calc(var(--space) / 2) 0;

  &__image {
    border-radius: 100%;
    width: 90px;
    height: 90px;
    margin-bottom: 1em;
  }

  &__intro {
    opacity: 0.8;
  }

  &__site-title {
    font-size: 1.5em;
  }

  &__links {
    margin-top: 2.5em;
    a {
      display: inline-block;
      vertical-align: middle;
      margin: 0 0.5em;
    }
  }
  .toggle-theme {
    margin-top: 2rem;
  }
}
</style>