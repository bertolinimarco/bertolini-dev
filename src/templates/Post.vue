<template>
  <Layout>
    <div class="post-title">
      <h1 class="post-title__text">{{ $page.post.title }}</h1>
      <PostMeta :post="$page.post"/>
      <!-- <alert
        v-if="postIsOlderThanOneYear"
      >This post is over a year old, some of this information may be out of date.</alert>-->
    </div>

    <div class="post content-box">
      <div class="post__header">
        <g-image alt="Cover image" v-if="$page.post.coverImage" :src="$page.post.coverImage"/>
      </div>

      <div class="post__content" v-html="$page.post.content"/>

      <div class="post__footer">
        <PostTags :post="$page.post"/>
      </div>
    </div>

    <Author class="post-author"/>
  </Layout>
</template>

<script>
// import dayjs from "dayjs";
// import Alert from "~/components/Alert";
import PostMeta from "~/components/PostMeta";
import PostTags from "~/components/PostTags";
import Author from "~/components/Author.vue";

export default {
  components: {
    // Alert,
    Author,
    PostMeta,
    PostTags
  },
  metaInfo() {
    return {
      title: this.$page.post.title,
      meta: [
        {
          name: "description",
          content: this.$page.post.description
        }
      ]
    };
  }
  // computed: {
  //   postIsOlderThanOneYear() {
  //     let postDate = dayjs(this.$page.post.date);
  //     return dayjs().diff(postDate, "y") > 0 ? true : false;
  //   }
  // }
};
</script>

<page-query>
query Post ($path: String!) {
  post: post (path: $path) {
    title
    path
    date (format: "MMMM YYYY")
    timeToRead
    tags {
      id
      title
      path
    }
    description
    content
  }
}
</page-query>

<style lang="scss">
.post-title {
  padding: calc(var(--space) / 2) 0 calc(var(--space) / 2);
  text-align: center;
  max-width: var(--content-width);
  margin: 0 auto;
}

.post-author {
  background: var(--bg-content-color);
}

.post {
  &__header {
    width: calc(100% + var(--space) * 2);
    margin-left: calc(var(--space) * -1);
    margin-top: 0;
    margin-bottom: calc(var(--space) / 2);
    overflow: hidden;

    img {
      width: 100%;
    }

    &:empty {
      display: none;
    }
  }

  &__content {
    h2:first-child {
      margin-top: 0;
    }

    p:first-of-type {
      font-size: 1.2em;
      color: var(--title-color);
    }

    img {
      width: calc(100% + var(--space) * 2);
      margin-left: calc(var(--space) * -1);
      display: block;
      max-width: none;
    }
  }

  &__footer {
    padding: calc(var(--space) / 2) 0 calc(var(--space) / 2);
    margin: var(--space) 0 0;
  }
}
</style>