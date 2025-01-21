<template>
  <div class="button-wrapper">
    <button @click="handleClick">Przycisk {{ index + 1 }}</button>
    <p>Licznik: {{ counter }}</p>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    index: Number, // Indeks przycisku
    counter: Number // Wartość licznika
  },
  methods: {
    handleClick() {
      // Emitujemy zdarzenie do rodzica (App.vue)
      this.$emit('increment');
    }
  }
};
</script>

<style scoped>
.button-wrapper {
  text-align: center;
}
button {
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
}
</style>
