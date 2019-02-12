<template>
  <div id="app">
    <Nav></Nav>
    <router-view />
  </div>
</template>

<script>
import Nav from "@/components/Nav";
export default {
  components: {
    Nav
  }
};
</script>

<style lang="css" src="./assets/css/reset.css"></style>
<style lang="scss" src="./assets/css/style.scss"></style>
