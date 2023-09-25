<template>
  <!-- <audio src='/src/assets/music/get_it_right.mp3'></audio>
  <div>
    <p>Volume</p>
    <input type="range" id="volume" min="0" max="2" value="1" step="0.01" />
  </div>
  <div>
    <p>Pan</p>
    <input type="range" id="panner" min="-1" max="1" value="0" step="0.01" />
  </div>
  <div>
    <button @click="togglePlay" data-playing="false" role="switch">
      <span>Play/Pause</span>
    </button>
  </div> -->
  <div>
    <TrackList></TrackList>
  </div>
</template>

<script>
import TrackList from '../components/TrackList.vue';

export default {
    data() {
        return {
            audioContext: null,
            audio: null,
            track: null,
            audioElement: null,
            playButton: null,
        };
    },
    // mounted() {
    //     this.audioContext = new AudioContext();
    //     this.audioElement = document.querySelector("audio");
    //     this.track = this.audioContext.createMediaElementSource(this.audioElement);
    //     this.track.connect(this.audioContext.destination);
    //     this.playButton = document.querySelector("button");
    //     const gainNode = this.audioContext.createGain();
    //     const pannerOptions = { pan: 0 };
    //     const panner = new StereoPannerNode(this.audioContext, pannerOptions);
    //     const pannerControl = document.querySelector("#panner");
    //     pannerControl.addEventListener("input", () => {
    //         panner.pan.value = pannerControl.value;
    //     }, false);
    //     const volumeControl = document.querySelector("#volume");
    //     volumeControl.addEventListener("input", () => {
    //         gainNode.gain.value = volumeControl.value;
    //     }, false);
    //     this.track.connect(gainNode).connect(panner).connect(this.audioContext.destination);
    //     this.audioElement.addEventListener("ended", () => {
    //         playButton.dataset.playing = "false";
    //     }, false);
    // },
    methods: {
        togglePlay() {
            if (this.audioContext.state === "suspended") {
                this.audioContext.resume();
            }
            if (this.playButton.dataset.playing === "false") {
                this.audioElement.play();
                this.playButton.dataset.playing = "true";
            }
            else if (this.playButton.dataset.playing === "true") {
                this.audioElement.pause();
                this.playButton.dataset.playing = "false";
            }
        }
    },
    components: { TrackList }
};
</script>