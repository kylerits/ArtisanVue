<template lang="html">

  <header>

    <!-- Logo -->
    <div class="logo">
      <h2 class="logo-title">Artisan</h2>
      <p class="logo-text">
        <small>curated by <a href="https://reddit.com/r/artisanvideos">r/ArtisanVideos</a></small>
      </p>
    </div>

    <!-- Navigation -->
    <div class="navigation">

      <!-- Action Buttons -->
      <ul class='action-buttons'>
        <li><button type="button" name="search" class="nav-btn" @click="show = !show">Search</button></li>
        <li><button type="button" name="open" class="nav-btn" @click="visible = !visible">
          <span v-if="!visible">Open</span>
          <span v-else>Close</span>
        </button></li>
      </ul>

      <transition name="slide-fade">
        <search-form key="1" v-if="show"></search-form>
      </transition>

      <transition name="slide-fade">
        <my-aside key="2" v-if="visible"></my-aside>
      </transition>

    </div>

  </header>

</template>

<script>

  import MyAside from './Aside.vue'
  import SearchForm from './SearchForm.vue'

  export default {
    components: {
      MyAside,
      SearchForm
    },
    data () {
      return {
        visible: false,
        show: false
      }
    }
  }
</script>

<style lang="scss">

  @import "../assets/scss/variables.scss";

  header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 2em;

    .logo {
      .logo-title {
        font-size: 3em;
        font-weight: normal;
        margin: 0;
      }
      .logo-text {
        margin: 0;
      }
    }

    .navigation {

      position: relative;

      ul.action-buttons {
        li {
          display: inline-block;
        }
      }
    }
  }

  // Transition Component Styling

  .slide-fade-enter-active {
    transition: all .2s ease;
  }
  .slide-fade-leave-active {
    transition: all .3s cubic-bezier(1.0, 0.5, 0.8, 1.0);
  }
  .slide-fade-enter, .slide-fade-leave-to {
    transform: translateX(30px);
    opacity: 0;
  }

</style>
