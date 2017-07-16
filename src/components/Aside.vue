<template lang="html">

  <aside id="aside" class="js-tilt" data-tilt data-tilt-perspective="500">
    <section class="categories">
      <!-- List of Different Categories -->
      <h2>Category Cloud</h2>
      <video-categories></video-categories>
    </section>
  </aside>

</template>

<script>
import VideoCategories from './VideoCategories.vue'
import VanillaTilt from 'vanilla-tilt'

export default {
  props: ['visible'],
  components: {
    VideoCategories,
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

  #aside {
    position: absolute;
    right: 0;
    width: 33vw;
    min-width: 300px;
    height: auto;
    z-index: 10;
    background-color: whitesmoke;
    padding: 1em;
    box-sizing: border-box;
    transform-style: preserve-3d;
  }

</style>
