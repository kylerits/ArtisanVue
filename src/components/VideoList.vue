<template lang="html">

  <div class="video-list js-tilt" data-tilt data-tilt-perspective="500">
    <video-list-item
      v-for="video in videos"
      v-if="displayList( video.category )"
      :key='video.key'
      :title='video.title'
      :link='video.link'
      :category='video.category'
      :user='video.user'
      :userLink='video.userLink'
      :date='video.date'
      :timestamp='video.timestamp'
      ></video-list-item>
      <div class="empty" v-if="noCategories">
        Sorry. There are currently no videos in this category available.
      </div>
  </div>

</template>

<script>

  import VideoListItem from './VideoListItem.vue'
  import VanillaTilt from 'vanilla-tilt'
  import { bus } from '../main.js'

  export default {
    components: {
      VideoListItem,
      VanillaTilt
    },
    data () {
      return {
        showVideoCat: 'all',
        noCategories: false,
        videos: [
          {
            key: '1',
            title: "This is a video's title. I'm seeing if it passes through props.",
            link: '#',
            category: 'meta',
            user: 'u/User',
            userLink: '#',
            date: '10/10/16',
            timestamp: '30:00'
          },
          {
            key: '2',
            title: "This is another video.",
            link: '#',
            category: 'design',
            user: 'u/User2',
            userLink: '#',
            date: '10/11/16',
            timestamp: '10:00'
          },
          {
            key: '3',
            title: "Lorem ipsum dolor sit amet",
            link: '#',
            category: 'production',
            user: 'u/User3',
            userLink: '#',
            date: '10/12/16',
            timestamp: '10:00'
          },
          {
            key: '4',
            title: "Lorem ipsum dolor sit amet",
            link: '#',
            category: 'maintenance',
            user: 'u/User4',
            userLink: '#',
            date: '10/12/16',
            timestamp: '10:00'
          },
          {
            key: '5',
            title: "Lorem ipsum dolor sit amet",
            link: '#',
            category: 'performance',
            user: 'u/User4',
            userLink: '#',
            date: '10/12/16',
            timestamp: '6:00'
          },
          {
            key: '6',
            title: "Lorem ipsum dolor sit amet",
            link: '#',
            category: 'culinary',
            user: 'u/User4',
            userLink: '#',
            date: '10/12/16',
            timestamp: '12:00'
          },
          {
            key: '7',
            title: "Lorem ipsum dolor sit amet",
            link: '#',
            category: 'modification',
            user: 'u/User4',
            userLink: '#',
            date: '10/12/16',
            timestamp: '9:00'
          }
        ]
      }
    },
    methods: {
      displayList ( videoCategory ) {
        var category = videoCategory
        if ( this.showVideoCat === 'all' ) {

          return true

        } else if ( this.showVideoCat === videoCategory ) {

          return true

        }

      }
    },
    mounted () {
      const element = document.querySelector('.js-tilt')

      VanillaTilt.init( element, {
        max: 10,
        speed: 600,
        perspective: 1000
      })

    },
    created () {
      bus.$on('changeCategory', ( value ) => {
        this.showVideoCat = value
      })
    }
  }
</script>

<style lang="scss">
  @import "../assets/scss/variables.scss";

  .video-list {
    padding: 0;
    transform-style: preserve-3d;
    box-shadow: $drop-shadow;

    max-height: 500px;
    overflow-y: scroll;

    .video-list-item:nth-child(odd) {
      background-color: white;
    }
  }

</style>
