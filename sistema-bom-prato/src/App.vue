<template>
  <HomePage msg="Welcome to Your Vue.js App"/>
</template>

<script>
import HomePage from "@/components/Home/HomePage";
// import { BootstrapVue, IconsPlugin } from 'bootstrap-vue'

export default {
  name: 'App',
  components: {
    HomePage,
  },
  import: {
    // BootstrapVue,
    // IconsPlugin
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Roboto', sans-serif;
}
</style>
