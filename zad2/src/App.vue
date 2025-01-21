<template>
  <div id="app">
    <div class="button-container">
      <HelloWorld v-for="(counter, index) in counters" 
                  :key="index" 
                  :index="index"
                  :counter="counter"
                  @increment="increment(index)" />
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
      // Inicjalizujemy tablicę z 20 licznikami
      counters: Array(20).fill(0)
    };
  },
  methods: {
    increment(index) {
      // Zwiększamy licznik o 1 dla danego indeksu
      this.counters[index]++;
    }
  }
};
</script>

<style>
.button-container {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
  max-width: 600px;
  margin: 20px auto;
}
</style>
