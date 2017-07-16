<template lang="html">

  <div class="video-list-item default js-tilt" data-tilt data-tilt-perspective="500">

    <div class="video-info">

      <h3 class="video-title"><a href="#">This is a video's title. It's here to give me an idea for a string length. - [30:00]</a></h3>

      <p class="video-meta"><span class="tag">Category</span> submitted at <span class="date-time">Time</span> by <a href="#">u/User</a></p>

    </div>

    <div class="video-button-area">
      <button type="button" name="PlayVideo" class="btn-icon btn-play">
        <span class="ion-ios-play-outline"></span>
      </button>
    </div>

  </div>

</template>

<script>

  import VanillaTilt from 'vanilla-tilt'

  export default {
    components: {
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

  @import "../assets/scss/variables.scss";

  .video-list-item {
    list-style-type: none;
    display: block;
    width: 100%;
    background-color: $off-white;
    display: flex;
    justify-content: space-between;
    box-sizing: border-box;

    transform-style: preserve-3d;

    box-shadow: $drop-shadow;

    .video-info {
      padding: 1em;
      transform: translateZ(10px) scale(.95);

      .video-title {
        margin-bottom: .5em;
      }

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
        }
      }
    }

    .video-button-area {
      width: 100px;
      display: flex;
      justify-content: center;
      align-items: center;
      border-left: solid 1px lightgrey;

      button {
        transform: translateZ(10px) scale(.8);
      }
    }

    // Category Specific Styles
    &.default {
      border-left: solid .5em grey;
    }
  }

</style>
