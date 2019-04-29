<template>
  <Layout :show-logo="false" :show-nav="false" class="is-homepage">
    <Author :show-title="true" :shownavlinks="true"/>
  </Layout>
</template>

<script>
import Author from "~/components/Author.vue";

export default {
  components: {
    Author
  },
  metaInfo: {
    title: "Marco Bertolini - Front End Developer"
  }
};
</script>
