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

* {
    box-sizing: border-box;
}

body {
  background-color: $main-background-colour;
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif; 
  font-size: 18px;
  margin-top: 10px;
  color: $black;
}

</style>
