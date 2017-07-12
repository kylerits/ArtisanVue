<template lang="html">

  <div class="video-list">
    <video-list-item></video-list-item>
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
