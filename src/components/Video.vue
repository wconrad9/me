<template>
    <div id="youtube-player"></div>
  </template>
  
  <script>
import { onUnmounted } from 'vue'

  export default {
    mounted() {
      // Load the YouTube API script
      const tag = document.createElement('script')
      tag.src = 'https://www.youtube.com/iframe_api'
      const firstScriptTag = document.getElementsByTagName('script')[0]
      firstScriptTag.parentNode.insertBefore(tag, firstScriptTag)
  
      // Set up the YouTube player
      window.onYouTubeIframeAPIReady = () => {
        new window.YT.Player('youtube-player', {
          videoId: 'HIPXk4PqL-s',
          playerVars: {
            autoplay: 0,
            controls: 1,
            modestbranding: 1,
            rel: 0,
            showinfo: 0
          },
          events: {
            onReady: () => {
              console.log('YouTube player is ready.')
            },
            onStateChange: event => {
              console.log('YouTube player state changed:', event.data)
            }
          }
        })
      }
    }
  }
  </script>