<template lang="html">

  <ul class="category-list">
    <li v-for="category in categories">
      <a :href="'#' + category" class="category" :class="category" @click="changeCategory( category )">{{ category }}</a>
    </li>
  </ul>

</template>

<script>
  import {bus} from '../main.js'

  export default {
    data () {
      return {
        categories: [
          'all',
          'maintenance',
          'production',
          'design',
          'performance',
          'culinary',
          'modification',
          'meta',
          'other'
        ]

      }
    },
    methods: {
      changeCategory ( cat ) {
        var newCategory = cat
        bus.$emit('changeCategory', newCategory)
      }
    }
  }
</script>

<style lang="scss">

  @import "../assets/scss/variables.scss";

  .category-list {

    margin: 0;
    padding: 0;
    transform: translateZ(40px);
    text-align: center;
    transform-style: preserve-3d;

    li {
      display: inline-block;
      box-sizing: border-box;
      margin: .8em .5em;
      transition: all .2s ease;

      &:hover {
        transform: translateZ(50px);
      }

      a.category {
        padding: .5em 1em;
        border-radius: 1em;
        background-color: lightgrey;
        box-sizing: border-box;
        color: white;
        letter-spacing: 1px;

        &.all { }

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

        &.other {}

      }
    }
  }
</style>
