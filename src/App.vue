<template>
  <app-header />
  <router-view/>
</template>

<script>

import AppHeader from "@/components/AppHeader.vue";

export default {
  components: {
    AppHeader
  }
}
</script>

<style lang="scss">
@import "@/assets/styles/variables.scss";

body {
  background-color: $main-background-colour;
}

</style>
