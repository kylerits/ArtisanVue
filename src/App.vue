<template>

  <main id="app">

    <!-- Header Area -->
    <create-header></create-header>


    <!-- Main Area -->
    <div class="container">

      <!-- Player Section -->
      <section id="player">

        <transition name="slide-fade-up">
          <div class="section-header standIn" v-if="!playerVisible">
            <!-- Initial Message -->
            <h2>App Title and Information</h2>
            <p>Lorem ipsum dolor sit amet, mea ea duis laudem, scripta splendide pro ne. Mei no choro putent bonorum, mea eu velit tibique.</p>
          </div>
        </transition>

        <!-- Video Player (Initialized either when 'random' is selected or a video is selected from the list.) -->

        <transition name="slide-fade-in">
          <div class="player" v-if="playerVisible">
            <!-- Initial Message -->
            <h2 class="videoTitle"><a :href="link">{{ title }}</a></h2>
            <p class="video-meta"><span class="tag" :class="category">{{ category }}</span> submitted at <span class="date-time">{{ date }}</span> by <a :href="userLink">{{ user }}</a></p>
          </div>
        </transition>

      </section>

      <!-- List Section -->
      <section id="listing">

        <div class="section-header">
          <h2 class="category-header">{{ categoryMain }}</h2>
        </div>

        <!-- List of Videos to Play -->
        <video-list></video-list>

      </section>

    </div>

    <!-- Footer Area -->
    <footer>

    </footer>

  </main>


</template>

<script>

import {bus} from './main.js'
import CreateHeader from './components/CreateHeader.vue'
import VideoList from './components/VideoList.vue'

export default {
  name: 'app',
  components: {
    CreateHeader,
    VideoList
  },
  data () {
    return {
      categoryMain: 'all',
      playerVisible: false,
      title: '',
      link: '',
      category: '',
      user: '',
      userLink: '',
      date: '',
      timestamp: ''
    }
  },
  created () {
    bus.$on('changeCategory', ( value ) => {
      this.categoryMain = value
    }),
    bus.$on('pushVideo', ( video ) => {
      
      this.playerVisible = true

      this.title = video.title
      this.link = video.link
      this.category = video.category
      this.user = video.user
      this.userLink = video.userLink
      this.date = video.date
      this.timestamp = video.timestamp

    })
  }
}
</script>

<style lang="scss">

  @import "./assets/scss/variables.scss";
  @import "./assets/scss/global.scss";

  #app {
    font-family: 'Alias', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;

    max-width: 1500px;
    margin: 0 auto;
  }

  .container {
    display: flex;
    flex-wrap: wrap;

    section {
      width: 50%;
      min-width: 250px;
      padding: 2em;
      box-sizing: border-box;

      .player {
        box-shadow: $drop-shadow;
        padding: 2em;

        .video-meta {
          font-size: .8em;
          color: grey; //change to lighter font-color
          margin: 0;

          .tag {
            padding: .5em 1em;
            font-size: .8em;
            text-transform: uppercase;
            letter-spacing: .5px;
            color: white;
            background-color: grey;
            border-radius: 2em;

            &.maintenance {
              background-color: $color-maintenance;
            }

            &.production {
              background-color: $color-production;
            }

            &.design {
              background-color: $color-design;
            }

            &.performance {
              background-color: $color-performance;
            }

            &.culinary {
              background-color: $color-culinary;
            }

            &.modification {
              background-color: $color-modification;
            }

            &.meta {
              background-color: $color-meta;
            }
          }
        }
      }

      .section-header {

        &.standIn {
          box-shadow: $drop-shadow;
          padding: 2em;
        }

        .category-header {
          text-transform: capitalize;
        }
      }
    }
  }

  // Transition Component Styling

  .slide-fade-up-enter-active {
    transition: all .2s ease;
  }
  .slide-fade-up-leave-active {
    transition: all .2s cubic-bezier(1.0, 0.5, 0.8, 1.0);
  }
  .slide-fade-up-enter, .slide-fade-up-leave-to {
    transform: translateY(-30px);
    opacity: 0;
  }

  .slide-fade-in-enter-active {
    transition: all .2s ease .25s;
  }
  .slide-fade-in-leave-active {
    transition: all .2s cubic-bezier(1.0, 0.5, 0.8, 1.0) .25s;
  }
  .slide-fade-in-enter {
    transform: translateY(30px);
    opacity: 0;
  }
  .slide-fade-in-leave-to {
    transform: translateY(-30px);
    opacity: 0;
  }

  // Media Queries

  @media screen and ( max-width: 900px ) {
    .container {
      section {
        width: 100%;
      }
    }
  }

</style>
