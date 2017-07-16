<template lang="html">
  <aside id="search-form">
    <form class="search-form">
      <input type="text" name="search-input" placeholder="Search">
      <button type="button" name="submitSearch" class="btn-icon submit"><span class="ion-ios-search"></span></button>
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
    min-width: 300px;
    height: auto;
    z-index: 10;
    background-color: whitesmoke;
    padding: 2em;
    box-sizing: border-box;

    .search-form {

      position: relative;

      input[name="search-input"] {

        background-color: transparent;
        padding: .5em 0;
        width: 100%;
        line-height: 1.5em;
        border: none;
        border-bottom: 2px solid black;
        outline: none;

      }

      button.submit {
        font-size: 1.5em;
        position: absolute;
        right: 0;
        top: .1em;
      }
    }
  }

</style>
