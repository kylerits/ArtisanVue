<template lang="html">

  <aside id="aside">
    <section class="categories">
      <!-- List of Different Categories -->
      <video-categories></video-categories>
    </section>
  </aside>

</template>

<script>
import VideoCategories from './VideoCategories.vue'

export default {
  props: ['visible'],
  components: {
    VideoCategories
  }
}
</script>

<style lang="scss">

  #aside {
    position: absolute;
    right: 0;
    width: 33vw;
    height: auto;
    z-index: 10;
    background-color: whitesmoke;
    padding: 1em;
    box-sizing: border-box;
  }

</style>
