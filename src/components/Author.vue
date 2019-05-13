<template>
  <div class="author">
    <g-image
      alt="Marco Bertolini"
      class="author__image"
      src="https://pbs.twimg.com/profile_images/832656663647707140/9rNz5PXO_400x400.jpg"
      blur="5"
    />

    <h1>Ciao, I'm Marco</h1>

    <h2 class="author__intro" v-on:click="getQuote">{{quote}}</h2>

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
  },
  data: function() {
    return {
      random: 1,
      quote: "",
      quotes: [
        "I'm a Front End Developer who remembers when websites were only a bunch of tables.",
        "I'm a strange designer/developer hybrid",
        "I ❤️ CSS",
        "My top skill is turning design into code",
        "I convert design into code since 2008",
        "I'm online since 1999"
      ]
    };
  },
  methods: {
    // Randmize quotes
    getQuote: function() {
      this.random = Math.floor(Math.random() * 6) + 0;
      this.quote = this.quotes[this.random];
    }
  },
  // Load quotes on page load
  beforeMount() {
    this.getQuote();
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
    font-size: 1.2rem;
    padding: 0 1rem;
    margin: 0;
    font-weight: 300;
    opacity: 0.8;
    max-width: calc(var(--content-width) / 1.5);
    margin: 0 auto;
    &:hover {
      cursor: help;
    }
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