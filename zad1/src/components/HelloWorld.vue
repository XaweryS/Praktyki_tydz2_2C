<template>
  <div class="galeria">
    <h1>Galeria zdjęć</h1>
    <div class="gp">
      <div v-for="(zdj, i) in zdj" :key="i" class="wz">
        <img :src="zdj.url" :alt="zdj.title" />
        <p>{{ zdj.title }}</p>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      zdj: [
        { url: require('@/assets/kd.jpeg'), title: "Krzywy Las" },
        { url: require('@/assets/pies.jpeg'), title: "Dwa Psy" },
        {url: require('@/assets/lot.jpeg'), title: "Samolot Lot" },
        { url: require('@/assets/dom.jpeg'), title: "Dom Jednorodzinny" },
      ],
    };
  },
};
</script>

<style>
.galeria{
  text-align: center;
  background-color: black;
}
.gp{
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 20px;
}

.wz{
  border: 3px solid #E545BC;
  border-radius: 8px;
  overflow: hidden;
}

img{
  width: 100%;
  height: auto;
}
p{
  margin: 0;
  padding: 15px;
  background-color: black;
}
</style>
