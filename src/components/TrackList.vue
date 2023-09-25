<template>
    <div class="track-list">
      <div v-for="track in tracks" :key="track.id" class="track">
        <img :src="track.albumCover" alt="Album Cover" class="album-cover" />
        <div class="metadata">
          <h3>{{ track.title }}</h3>
          <p>{{ track.artist }}</p>
          <p>{{ track.duration }}</p>
        </div>
        <button @click="togglePlayback(track)">
          {{ currentTrack === track && isPlaying ? 'Pause' : 'Play' }}
        </button>
      </div>
    </div>
</template>

<script>
export default {
data() {
    return {
    tracks: [
        {
        id: 4,
        title: 'shuffle king',
        artist: 'Walt Conrad',
        albumCover: 'src/assets/images/album_art/15.png',
        audioSrc: 'src/assets/music/shuffle_king1.mp3',
        duration: '2:59',
        },
        {
        id: 1,
        title: 'get it right',
        artist: 'Walt Conrad',
        albumCover: 'src/assets/images/album_art/get_it_right_cover.jpg',
        audioSrc: 'src/assets/music/get_it_right.mp3',
        duration: '2:20'
        },
        {
        id: 2,
        title: 'flux',
        artist: 'Walt Conrad',
        albumCover: 'src/assets/images/album_art/sporadic_rain.jpg',
        audioSrc: 'src/assets/music/flux.mp3',
        duration: '4:26'
        },
        {
        id: 3,
        title: 'hailey',
        artist: 'Walt Conrad',
        albumCover: 'src/assets/images/album_art/hailey.jpg',
        audioSrc: 'src/assets/music/hailey.mp3',
        duration: '3:14'
        },
        // Add other tracks similarly...
    ],
    currentTrack: null,
    audio: new Audio(),
    isPlaying: false
    };
},
methods: {
    togglePlayback(track) {
    if (this.isPlaying && this.currentTrack === track) {
        this.audio.pause();
    } else {
        if (this.currentTrack !== track) {
        this.audio.src = track.audioSrc;
        this.currentTrack = track;
        }
        this.audio.play();
    }
    this.isPlaying = !this.isPlaying;
    }
},
watch: {
    isPlaying(value) {
    if (!value) {
        this.audio.pause();
    }
    }
}
};
</script>

<style scoped>
.track-list {
display: flex;
flex-direction: column;
gap: 20px;
}

.track {
display: flex;
align-items: center;
gap: 15px;
}

.album-cover {
width: 60px;
height: 60px;
object-fit: cover;
border-radius: 5px;
}

.metadata {
flex-grow: 1;
}
</style>
  