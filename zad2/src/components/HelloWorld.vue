<template>
  <div class="przycisk">
    <button @click="kl">Przycisk {{ i + 1 }}</button>
    <p>Liczba: {{ licz }}</p>
  </div>
</template>
<script>
export default {
  name: 'HelloWorld',
  props: {
    i: Number, 
    licz: Number 
  },
  methods: {
    kl() {
      this.$emit('dziala');
    }
  }
};
</script>
<style>
.przycisk {
  text-align: center;
}
button {
  margin-top: 20px;
  margin-left: 20px;
  padding: 10px 20px;
  font-size: 20px;
  cursor: pointer;
}
</style>
