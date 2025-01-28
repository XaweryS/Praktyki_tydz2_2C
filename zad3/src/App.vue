<template>
  <div class="sg">
    <ban />
    <div class="srod">
      <lew />
      <csro/>
      <pra/>
    </div>
    <stopka/>
  </div>
</template>

<script>
import ban from './components/ban.vue';
import csro from './components/csro.vue';
import lew from './components/lew.vue';
import pra from './components/pra.vue';
import stopka from './components/stopka.vue';

export default {
  name: 'App',
  components: {
    ban,
    csro,
    lew,
    pra,
    stopka
  }
};
</script>

<style>
.sg {
  flex-direction: column;
  height: 1010px;
}
.srod {
  display: flex;a
}
.lp, .pp {
  width: 20%;
  height: 755px;
}
.sro {
  width: 60%;
  height: 755px;
}
</style>