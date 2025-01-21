<template>
  <div id="app">
    <div class="button-container">
      <HelloWorld v-for="(licz, i) in licz2" 
        :key="i" 
        :i="i"
        :licz="licz"
        @dziala="increment(i)" />
    </div>
  </div>
</template>
<script>
import HelloWorld from './components/HelloWorld.vue';

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data() {
    return {
      licz2: Array(20).fill(0)
    };
  },
  methods: {
    increment(i) {
      this.licz2[i]++;
    }
  }
};
</script>
<style>
.button-container {
  border: 3px solid black;
  display: grid;
  grid-template-columns: repeat(4, 150px);
  gap: 30px;
  width: 710px;
  margin: 100px auto;
  border-radius: 10px;
}
</style>
