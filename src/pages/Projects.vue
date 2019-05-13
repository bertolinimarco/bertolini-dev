<template>
  <Layout :show-logo="true">
    <div class="page-title">
      <h1 class="page-title__text">Projects</h1>
    </div>
    <div class="content-box projects">
      <div class="block">
        <div class="block-header">
          <div class="block-title">🍎 Newton</div>
          <div class="block-meta">Theme</div>
        </div>
        <div class="block-body">
          <p>A low-eyestrain Editor/IDE Theme, apple not included.</p>
        </div>
        <div class="block-footer">
          <a href="#" target="_blank">Project</a>
          <a href="#" target="_blank">GitHub</a>
        </div>
      </div>
      <div class="block">
        <div class="block-header">
          <div class="block-title">🍕 Pizza</div>
          <div class="block-meta">PHP • CSS • JS</div>
        </div>
        <div class="block-body">
          <p>A very opinionated frontend starter</p>
        </div>
        <div class="block-footer">
          <a href="#" target="_blank">Project</a>
          <a href="#" target="_blank">GitHub</a>
        </div>
      </div>
      <div class="block">
        <div class="block-header">
          <div class="block-title">📓 Dash</div>
          <div class="block-meta">PHP • CSS • JS • UX</div>
        </div>
        <div class="block-body">
          <p>Backend starter</p>
        </div>
        <div class="block-footer">
          <a href="#" target="_blank">Project</a>
          <a href="#" target="_blank">GitHub</a>
        </div>
      </div>
      <!-- <div class="block">
        <div class="block-header">
          <div class="block-title">👨‍💻 Bertolini.dev</div>
          <div class="block-meta">Vue • CSS • JS</div>
        </div>
        <div class="block-body">
          <p>This blog</p>
        </div>
        <div class="block-footer">
          <a href="#" target="_blank">GitHub</a>
        </div>
      </div>-->
      <div class="block">
        <div class="block-header">
          <div class="block-title">📜 Aumyr</div>
          <div class="block-meta">Vue • Text</div>
        </div>
        <div class="block-body">
          <p>A free fantasy setting for roleplaying games</p>
        </div>
        <div class="block-footer">
          <a href="#" target="_blank">Project</a>
          <a href="#" target="_blank">GitHub</a>
        </div>
      </div>
    </div>
  </Layout>
</template>

<script>
import PostCard from "~/components/PostCard.vue";

export default {
  components: {
    PostCard
  },
  metaInfo: {
    title: "Projects"
  }
};
</script>
