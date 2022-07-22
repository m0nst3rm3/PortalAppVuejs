<template>
  <img alt="Realhr logo" src="./assets/logo-tag.png" height="50" width="250">
  <DemoPortal/>
</template>

<script>
import DemoPortal from "@/components/DemoPortal";
export default {
  name: 'App',
  components: {
    DemoPortal,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
</style>
