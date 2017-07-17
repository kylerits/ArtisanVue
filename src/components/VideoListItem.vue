<template lang="html">

  <div class="video-list-item" :class="category" >

    <div class="video-info">

      <h3 class="video-title"><a href="#">{{ title }} - [{{ timestamp }}]</a></h3>

      <p class="video-meta"><span class="tag" :class="category">{{ category }}</span> submitted at <span class="date-time">{{ date }}</span> by <a :href="userLink">{{ user }}</a></p>

    </div>

    <div class="video-button-area">
      <button type="button" name="PlayVideo" class="btn-icon btn-play" @click="pushVideo( title, link, category, user, userLink, date, timestamp )">
        <span class="ion-ios-play-outline"></span>
      </button>
    </div>

  </div>

</template>

<script>

  import { bus } from '../main.js'

  export default {
    props: ['title', 'link', 'category', 'user', 'userLink', 'date', 'timestamp'],
    methods: {
      pushVideo ( title, link, category, user, userLink, date, timestamp ) {

        var video = {

          title: title,
          link: link,
          category: category,
          user: user,
          userLink: userLink,
          date: date,
          timestamp: timestamp

        }

        bus.$emit( 'pushVideo', video )

      }
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

    .video-button-area {
      width: 100px;
      min-width: 100px;
      display: flex;
      justify-content: center;
      align-items: center;
      border-left: solid 1px lightgrey;

      button {
        transform: translateZ(10px) scale(.8);
      }
    }

    // Category Specific Styles
    &.all {
      border-left: solid .5em grey;
    }
    &.maintenance {
      border-left: solid .5em $color-maintenance;
    }
    &.production {
      border-left: solid .5em $color-production;
    }
    &.design {
      border-left: solid .5em $color-design;
    }
    &.performance {
      border-left: solid .5em $color-performance;
    }
    &.culinary {
      border-left: solid .5em $color-culinary;
    }
    &.modification {
      border-left: solid .5em $color-modification;
    }
    &.meta {
      border-left: solid .5em $color-meta;
    }
    &.other {
      border-left: solid .5em grey;
    }
  }

  @media screen and ( max-width: 500px ) {
    .video-list-item {


      .video-info {
        font-size: .8em;
      }

      .video-button-area {

        width: 80px;
        min-width: 80px;

        button {
          font-size: 1.7em;
        }
      }
    }
  }

</style>
