<template>
  <div class="post-meta">
    {{ post.date }} •
    <template v-if="post.timeToRead">
      <strong>{{ post.timeToRead }} min</strong>
    </template>
  </div>
</template>

<script>
export default {
  props: ["post"]
};
</script>

<style lang="scss">
.post-meta {
  opacity: 0.8;
}
</style>