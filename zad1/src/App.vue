<template>
  <div id="app">
    <HelloWorld />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
  },
};
</script>
<style>
body{
  background-color: black;
}
#app {
  font-family: italic;
  text-align: center;
  color: #1B44E6;
  margin-top: 180px;
}
</style>
