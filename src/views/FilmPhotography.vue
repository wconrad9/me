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
        '/src/assets/photographs/film/ChapelPlants_min.jpeg',
        '/src/assets/photographs/film/DreamyShip_min.jpg',
        '/src/assets/photographs/film/Jack_min.jpg',
        '/src/assets/photographs/film/LandscapeGoats_min.jpg',
        '/src/assets/photographs/film/LivWindow_min.jpg',
        '/src/assets/photographs/film/RussHunter_min.jpg',
        '/src/assets/photographs/film/SF_road_min.jpeg',
        '/src/assets/photographs/film/sporadic_rain_min.jpeg',
        '/src/assets/photographs/film/SunsetBeach1_min.jpeg',
        '/src/assets/photographs/film/SunValleyHillside_min.jpg',
        '/src/assets/photographs/film/VelmaLake3_min.jpg',
        '/src/assets/photographs/film/dock.landscape_min.jpg',
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