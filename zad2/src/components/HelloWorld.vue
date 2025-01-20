<template>
  <div class="gallery">
    <h1>Galeria zdjęć</h1>
    <div class="gallery-grid">
      <div
        v-for="(photo, index) in photos"
        :key="index"
        class="photo-card"
        @click="openModal(index)"
      >
        <img :src="photo.url" :alt="photo.title" />
        <p>{{ photo.title }}</p>
      </div>
    </div>

    <div v-if="showModal" class="modal" @click="closeModal">
      <div class="modal-content" @click.stop>
        <img :src="photos[selectedPhoto].url" :alt="photos[selectedPhoto].title" />
        <p>{{ photos[selectedPhoto].title }}</p>
        <button @click="closeModal">Zamknij</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      photos: [
        { url: "https://via.placeholder.com/300", title: "Zdjęcie 1" },
        { url: "https://via.placeholder.com/300", title: "Zdjęcie 2" },
        { url: "https://via.placeholder.com/300", title: "Zdjęcie 3" },
        { url: "https://via.placeholder.com/300", title: "Zdjęcie 4" },
      ],
      showModal: false,
      selectedPhoto: null,
    };
  },
  methods: {
    openModal(index) {
      this.selectedPhoto = index;
      this.showModal = true;
    },
    closeModal() {
      this.showModal = false;
    },
  },
};
</script>

<style scoped>
.gallery {
  text-align: center;
}

.gallery-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1rem;
}

.photo-card {
  cursor: pointer;
  border: 1px solid #ccc;
  border-radius: 8px;
  overflow: hidden;
  transition: transform 0.2s;
}

.photo-card:hover {
  transform: scale(1.05);
}

.photo-card img {
  width: 100%;
  height: auto;
}

.photo-card p {
  margin: 0;
  padding: 0.5rem;
  background: #f7f7f7;
}

.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.8);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
}

.modal-content {
  background: white;
  padding: 1rem;
  border-radius: 8px;
  max-width: 500px;
  text-align: center;
}

.modal-content img {
  width: 100%;
  height: auto;
  margin-bottom: 1rem;
}
</style>
