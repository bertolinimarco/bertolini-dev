<template>
  <div class="post-tags text-center">
    <g-link class="post-tags__link" v-for="tag in post.tags" :key="tag.id" :to="tag.path">
      <span>#</span>
      {{ tag.title }}
    </g-link>
  </div>
</template>

<script>
export default {
  props: ["post"]
};
</script>

<style lang="scss">
.post-tags {
  &__link {
    font-size: 0.8em;
    color: currentColor;
    text-decoration: none;
    background-color: var(--body-color);
    color: var(--bg-content-color) !important;
    padding: 0.5em 0.75rem;
    border-radius: var(--radius);
  }
  &__link + &__link {
    margin-left: .75em;
  }
}
</style>