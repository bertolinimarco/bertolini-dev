<template>
  <g-link class="logo" to="/">
    <g-image
      alt="Marco Bertolini"
      class="author__image"
      src="https://pbs.twimg.com/profile_images/832656663647707140/9rNz5PXO_400x400.jpg"
      blur="5"
    />
    <!-- <span class="logo__text">
	    &larr; {{ $static.metaData.siteName }}
    </span>-->
  </g-link>
</template>

<static-query>
query {
  metaData {
    siteName
  }
}
</static-query>

<style lang="scss">
.logo {
  text-decoration: none;
  color: var(--body-color) !important;
  font-size: 0.9em;

  img {
    margin: 0;
    vertical-align: middle;
    border-radius: 100%;
    height: 40px;
    width: 40px;
    margin-right: 0.5em;
  }
}
</style>