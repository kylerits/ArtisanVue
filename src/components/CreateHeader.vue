<template lang="html">

  <header>

    <!-- Logo -->
    <div class="logo">
      <h2 class="logo-title">{{ title }}</h2>
      <p class="logo-text">
        <small>curated by <a href="https://reddit.com/r/artisanvideos">r/ArtisanVideos</a></small>
      </p>
    </div>

    <!-- Navigation -->
    <div class="navigation">

      <!-- Action Buttons -->
      <ul class='action-buttons'>
        <li><button type="button" name="search" class="nav-btn">Search</button></li>
        <li><button type="button" name="open" class="nav-btn">Open</button></li>
      </ul>

      <div id="aside">
        <section class="categories">
          <!-- List of Different Categories -->
        </section>
        <section class="social">
          <!-- Links to my social media and github -->
        </section>
      </div>

    </div>

  </header>

</template>

<script>
export default {
  data () {
    return {
      title: 'Artisan',
      msg: 'Welcome to Your Vue.js App'
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
      ul.action-buttons {
        li {
          display: inline-block;
        }
      }
    }
  }

</style>
