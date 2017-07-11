<template>

  <main id="app">

    <!-- Header Area -->
    <header>

      <!-- Logo -->
      <div class="logo">
        <h2>Artisan</h2>
        <p>
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

    <!-- Main Area -->
    <div class="container">

      <!-- Player Section -->
      <section id="player">

        <div class="section-header">
          <!-- Initial Message -->
          <h2>Play a Random Video</h2>
          <!-- Plays a random video from the list. Or the first one. It's not really to important which. -->
          <button type="button" name="playRandom" class="btn">Play</button>
        </div>

        <!-- Video Player (Initialized either when 'random' is selected or a video is selected from the list.) -->

      </section>

      <!-- List Section -->
      <section id="listing">

        <div class="section-header">
          <h2>All</h2>
        </div>

        <!-- List of Videos to Play -->

      </section>

    </div>

    <!-- Footer Area -->
    <footer>

    </footer>

  </main>


</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<style lang="scss">

  #app {
    font-family: 'Alias', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
  }

</style>
