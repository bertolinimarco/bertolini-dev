<template>
  <Layout :show-logo="true">
    <div class="page-title">
      <h1 class="page-title__text">Blog</h1>
    </div>
    <div class="content-box posts">
      <PostCard v-for="edge in $page.posts.edges" :key="edge.node.id" :post="edge.node"/>
    </div>
  </Layout>
</template>

<page-query>
{
  posts: allPost (sortBy: "date", order: DESC) {
    edges {
      node {
        id
        title
        path
        date (format: "MMMM YYYY")
        timeToRead
      }
    }
  }
}
</page-query>

<script>
import PostCard from "~/components/PostCard.vue";

export default {
  components: {
    PostCard
  },
  metaInfo: {
    title: "Blog"
  }
};
</script>
