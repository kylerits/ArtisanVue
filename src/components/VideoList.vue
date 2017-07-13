<template lang="html">

  <div class="video-list">
    <video-list-item data-tilt data-tilt-max="50" data-tilt-speed="400" data-tilt-perspective="500"></video-list-item>
  </div>

</template>

<script>

import VideoListItem from './VideoListItem.vue'



export default {
  components: {
    VideoListItem
  }
}
</script>

<style lang="scss">

  .video-list {
    padding: 0;
  }

</style>
