<template>
  <div id="app">
    <router-view />
  </div>
</template>

<script>
import { serverRealTimeValues } from "./utils/register.js";

export default {
  name: "App",
  data() {
    return {
      server: null
    };
  },
  created() {
    serverRealTimeValues(value => {
      this.server = value;
    });
  }
};
</script>

<style>
html,
body,
iframe,
#app {
  height: 100%;
  overflow: hidden;
}
</style>
