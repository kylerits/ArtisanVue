<template lang="html">

  <aside id="aside">
    <section class="categories">
      <!-- List of Different Categories -->
    </section>
    <section class="social">
      <!-- Links to my social media and github -->
    </section>
  </aside>

</template>

<script>
export default {
  props: ['visible']
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
    padding: 2em;
    box-sizing: border-box;
  }

</style>
