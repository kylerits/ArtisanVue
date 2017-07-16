<template lang="html">

  <div class="video-list js-tilt" data-tilt data-tilt-perspective="500">
    <video-list-item></video-list-item>
    <video-list-item></video-list-item>
  </div>

</template>

<script>

import VideoListItem from './VideoListItem.vue'
import VanillaTilt from 'vanilla-tilt'


export default {
  components: {
    VideoListItem,
    VanillaTilt
  },
  mounted () {
    const element = document.querySelector('.js-tilt')

    VanillaTilt.init( element, {
      max: 10,
      speed: 600,
      perspective: 1000
    })

  }
}
</script>

<style lang="scss">
  @import "../assets/scss/variables.scss";

  .video-list {
    padding: 0;
    transform-style: preserve-3d;
    box-shadow: $drop-shadow;

    .video-list-item:nth-child(odd) {
      background-color: white;
    }
  }

</style>
