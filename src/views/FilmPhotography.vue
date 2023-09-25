<template>
    <div class="film-photography">
      <PhotoGallery :photos="photos" />
    </div>
</template>

<script>
import PhotoGallery from '@/components/PhotoGallery.vue';

export default {
  name: 'FilmPhotography',
  components: {
    PhotoGallery
  },
  data() {
    return {
      photos: [
        '/src/assets/photographs/film/group_water.jpg',
        '/src/assets/photographs/film/LassenMountaineering_min.jpg',
        '/src/assets/photographs/film/rainy_landscape_min.jpg',
        '/src/assets/photographs/film/SunsetBeachSurfer_min.jpg',
        '/src/assets/photographs/film/VelmaLake1_min.jpg',
      ]
    };
  }
};
</script>

<style scoped>
.film-photography {
  padding: 20px;
  text-align: center;
}
</style>