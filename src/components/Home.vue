<template>
    <div>
      <nav>
        <ul>
          <li @click="activeTab = 'About Me'" :class="{ 'active': activeTab === 'About Me' }">About Me</li>
          <li @click="activeTab = 'Code'" :class="{ 'active': activeTab === 'Code' }">Code</li>
          <li @click="activeTab = 'Photography'" :class="{ 'active': activeTab === 'Photography' }">Photography</li>
          <li @click="activeTab = 'Music'" :class="{ 'active': activeTab === 'Music' }">Music</li>
          <li @click="activeTab = 'Video'" :class="{ 'active': activeTab === 'Video' }">Video</li>
          <li @click="activeTab = 'Writing'" :class="{ 'active': activeTab === 'Writing' }">Writing</li>
        </ul>
      </nav>
  
      <div v-if="activeTab === 'About Me'">
        <AboutMe />
      </div>
  
      <div v-if="activeTab === 'Code'">
        <h2>Coding</h2>
        <!-- Add your content for Coding tab here -->
      </div>
  
      <div v-if="activeTab === 'Photography'">
        <h2>Photography</h2>
        <!-- Add your content for Photography tab here -->
      </div>
  
      <div v-if="activeTab === 'Music'">
        <Music />
      </div>

      <div v-if="activeTab === 'Writing'">
        <h2>Writing</h2>
        <!-- Add your content for Writing tab here -->
      </div>

      <div v-if="activeTab === 'Video'">
        <Video />
      </div>
    </div>
  </template>
  
  <script>
  import AboutMe from './AboutMe.vue';
  import Video from './Video.vue';
  import Music from './Music.vue';
  export default {
    data() {
      return {
        activeTab: 'About Me'
      }
    },
    components: {
        AboutMe,
        Video,
        Music,
    }
  }
  </script>
  
  <style>
  nav ul {
    display: flex;
    list-style: none;
    padding: 0;
    margin: 0;
  }
  
  nav li {
    padding: 10px;
    cursor: pointer;
  }
  
  nav li.active {
    background-color: #ccc;
  }
  
  h2 {
    margin-top: 0;
  }
  </style>
  