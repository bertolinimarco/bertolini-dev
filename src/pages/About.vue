<template>
  <Layout :show-logo="true">
    <div class="page-title">
      <h1 class="page-title__text">About</h1>
    </div>
    <div class="content-box">
      <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ipsum nostrum dolores atque similique ut sit quo repudiandae ex neque, itaque eos voluptates eveniet sunt commodi ratione quibusdam, fugiat ad! Modi.</p>
      <h3>Lorem, ipsum dolor.</h3>
      <ul>
        <li>1</li>
        <li>2</li>
        <li>3</li>
        <li>4</li>
      </ul>
    </div>
  </Layout>
</template>

<script>
import Author from "~/components/Author.vue";

export default {
  components: {
    Author
  },
  metaInfo: {
    title: "About"
  }
};
</script>
