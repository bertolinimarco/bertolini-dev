<template>
  <Layout>
    <div class="page-title">
      <h1 class="page-title__text">Post # {{ $page.tag.title }}</h1>
    </div>

    <div class="posts content-box">
      <PostCard v-for="edge in $page.tag.belongsTo.edges" :key="edge.node.id" :post="edge.node"/>
    </div>
  </Layout>
</template>

<page-query>
query Tag ($id: String!) {
  tag (id: $id) {
    title
    belongsTo {
      edges {
        node {
          ...on Post {
            title
            path
            date (format: "MMMM YYYY")
            timeToRead
            description
            coverImage
            content
          }
        }
      }
    }
  }
}
</page-query>

<script>
import Author from "~/components/Author.vue";
import PostCard from "~/components/PostCard.vue";

export default {
  components: {
    Author,
    PostCard
  }
};
</script>
