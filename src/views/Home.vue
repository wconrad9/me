<template>
    <div>
      <nav>
        <ul>
          <li @click="activeTab = 'None'" :class="{ 'active': activeTab === 'None' }">
            <img alt="Yin Yang" class="logo" src="/src/assets/Yin_yang.svg" width="25" height="25" />
          </li>
          <li @click="activeTab = 'ShuffleKing'" :class="{ 'active': activeTab === 'ShuffleKing' }">
            <img alt="shuffle_im" class="logo" src="/src/assets/icons/15.png" width="50" height="50" />
          </li>
          <li @click="activeTab = 'About'" :class="{ 'active': activeTab === 'About' }">About</li>
          <li @click="activeTab = 'Code'" :class="{ 'active': activeTab === 'Code' }">Code</li>
          <li @click="activeTab = 'Photography'" :class="{ 'active': activeTab === 'Photography' }">Photography</li>
          <li @click="activeTab = 'Music'" :class="{ 'active': activeTab === 'Music' }">Music</li>
          <li @click="activeTab = 'Video'" :class="{ 'active': activeTab === 'Video' }">Video</li>
          <li @click="activeTab = 'Writing'" :class="{ 'active': activeTab === 'Writing' }">Writing</li>
        </ul>
      </nav>
      
      <div v-if="activeTab === 'None'">
        <div class="video-container">
          <video autoplay preload loop>
              <source src="/src/assets/videos/landing_wdolg.mp4" type="video/mp4">
              Your browser does not support the video tag.
          </video>
        </div>
      </div>

      <div v-if="activeTab === 'ShuffleKing'">
        <video class="sk" autoplay preload loop>
              <source src="/src/assets/videos/ShuffleKing.0.mp4" type="video/mp4">
              Your browser does not support the video tag.
        </video>
      </div>
      
      <div v-if="activeTab === 'About'">
        <About />
      </div>
  
      <div v-if="activeTab === 'Code'">
        <br/>
        <p>
          I created an interactive map with Python, Streamlit, and Pandas to show the locations of the tallest
          mountains in the world!
        </p>
        <br/>
        <p>You can find source code <a href="https://github.com/wconrad9/tallest_mountains">here</a> on my Github!</p>
        <br/>
        <iframe 
          src="https://tallestmountains-nosfbqdqorv9hkaudweidv.streamlit.app/?embed=true"
          width="100%" 
          height="800px" 
          frameborder="0" 
          scrolling="yes">
        </iframe>
      </div>
  
      <div v-if="activeTab === 'Photography'">
        <FilmPhotography></FilmPhotography>
      </div>
  
      <div v-if="activeTab === 'Music'">
        <Music />
      </div>

      <div v-if="activeTab === 'Writing'">
        <br/>
        <p>We are born of earth and light.</p>
      </div>

      <div v-if="activeTab === 'Video'">
        <Video />
      </div>
    </div>
  </template>
  
  <script>
  import About from './About.vue';
  import Video from './Video.vue';
  import Music from './Music.vue';
  import FilmPhotography from './FilmPhotography.vue';
  export default {
    data() {
      return {
        activeTab: 'None'
      }
    },
    components: {
    About,
    Video,
    Music,
    FilmPhotography
}
  }
  </script>
  
  <style>
  
  body {
    overflow: hidden;
  }

  /* video styling */

  .video-container {
    position: relative;
    width: 100%;
    height: 100vh;  /* Adjust based on your design. */
  }

    video {
    object-fit: cover;
    width: 100vw;
    height: 100vh;
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }

  .sk {
      object-fit: cover;

      /* Setting width & height to auto prevents the video from being letterboxed */
      width: 100vw;
      height: 100vh;

      /* Center the video */
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
  }

  .content-over-video {
      position: absolute;
      bottom: 20%;  /* Adjust based on your design. */
      left: 5%;    /* Adjust based on your design. */
      z-index: 1;
      color: white; /* Or any color that provides contrast against your video */
  }

  nav ul {
    display: flex;
    list-style: none;
    padding: 0; 
    margin: 0;
    z-index: 1;
  }
  
  nav li {
    padding: 10px;
    cursor: pointer;
  }
  
  nav li.active {
    background-color: #811f88b9;
  }
  
  h1 {
    z-index: 1;
    font-style: italic;
  }

  h2 {
    margin-top: 0;
  }
  </style>
  