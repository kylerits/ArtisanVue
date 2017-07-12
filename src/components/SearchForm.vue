<template lang="html">
  <aside id="search-form">
    <form class="search-form">
      <input type="text" name="search-input" placeholder="Search">
      <input type="submit" name="search-button" value="Search">
    </form>
  </aside>
</template>

<script>
export default {
}
</script>

<style lang="scss">

  #search-form {
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
