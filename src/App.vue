<template>

  <main id="app">

    <!-- Header Area -->
    <create-header></create-header>


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

import CreateHeader from './components/CreateHeader.vue'

export default {
  name: 'app',
  components: {
    CreateHeader
  },
  data () {
    return {

    }
  }
}
</script>

<style lang="scss">

  @import "./assets/scss/variables.scss";

  body {
    margin: 0;
    box-sizing: border-box;
  }

  #app {
    font-family: 'Alias', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
  }

  a {
    color: $green;
  }

  button {
    cursor: pointer;
  }

  .container {
    display: flex;
    flex-wrap: wrap;

    section {
      width: 50%;
      min-width: 250px;
      padding: 2em;
      box-sizing: border-box;
    }
  }

</style>
