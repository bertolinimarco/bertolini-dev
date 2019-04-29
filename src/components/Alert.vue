<template>
  <div class="alert" role="alert">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "Alert"
};
</script>

<style lang="scss">
.alert {
  padding: 0.75rem;
  margin: 2rem 2rem 0;
  color: var(--body-color);
}
</style>
