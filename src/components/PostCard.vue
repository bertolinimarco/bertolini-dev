<template>
  <div class="block">
    <div class="block-header">
      <g-link :to="post.path">
        <div class="block-title" v-html="post.title"/>
      </g-link>
      <PostMeta class="block-meta" :post="post"/>
    </div>
    <!-- <p v-html="post.description"/> -->
    <!-- <PostTags class="post-card__tags" :post="post"/> -->
  </div>
</template>

<script>
import PostMeta from "~/components/PostMeta";
import PostTags from "~/components/PostTags";

export default {
  components: {
    PostMeta,
    PostTags
  },
  props: ["post"]
};
</script>

<style lang="scss">
.block {
  margin: 0 0 var(--space);
  .block-header {
    display: flex;
    justify-content: space-between;
    @media screen and (max-width: 650px) {
      display: inline-block;
    }
  }
  .block-footer {
    a {
      color: var(--link-color);
    }
    a + a {
      margin: 0 10px;
    }
  }
  a:hover {
    color: var(--link-color);
  }
  .block-title {
    font-weight: bold;
    font-size: 22px;
  }
  .block-meta {
    width: 100%;
    font-size: 0.8em;
    max-width: 300px;
    text-align: right;
    color: #676767;
    font-weight: bold;
    @media screen and (max-width: 650px) {
      max-width: 100%;
      text-align: left;
    }
  }
  @media screen and (max-width: 650px) {
    display: inline-block;
    justify-content: initial;
    width: 100%;
  }
}
</style>