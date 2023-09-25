<template>
  <div class="photo-gallery">
    <div v-for="(photo, index) in photos" :key="index" class="photo-container">
      <img :src="photo" alt="Film Photography" @click="openLightbox(index)" />
    </div>

    <EasyLightbox
      :visible="visibleRef"
      :imgs="photos"
      :index="indexRef"
      @hide="closeLightbox" />

  </div>
</template>

<script>
import EasyLightbox from 'vue-easy-lightbox';
import { ref, defineComponent } from 'vue';

export default {
  name: 'PhotoGallery',
  components: {
    EasyLightbox
  },
  props: {
    photos: {
      type: Array,
      required: true
    }
  },
  setup() {
    const indexRef = ref(0);
    const visibleRef = ref(false);

    const openLightbox = (index) => {
      indexRef.value = index;
      visibleRef.value = true;
      onShow();
    }
    
    const closeLightbox = () => {
      visibleRef.value = false;
    }

    const onShow = () => {
      visibleRef.value = true
    }

    return {
      indexRef,
      visibleRef,
      onShow,
      closeLightbox,
      openLightbox,
    }
  },
  data() {
    return {
      isLightboxOpen: false,
      currentImageIndex: 0,
    };
  },
};
</script>
  
  <style scoped>
  .photo-gallery {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    justify-content: center;
  }
  
  .photo-container img {
    max-width: 90%; 
    border: 3px solid #ccc;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    transition: transform 0.2s;
  }
  
  .photo-container img:hover {
    transform: scale(1.05);
  }
  </style>
  