<template lang="html">

  <ul class="category-list">
    <li v-for="category in categories">
      <a :href="'#' + category" class="category" :class="category" @click="changeCategory( category )">{{ category }}</a>
    </li>
  </ul>

</template>

<script>
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
        this.$emit('changeCategory', newCategory)
      }
    }
  }
</script>

<style lang="scss">

  @import "../assets/scss/variables.scss";

  .category-list {

    margin: 0;
    padding: 0;

    li {
      display: inline-block;
      box-sizing: border-box;
      margin: .8em;

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
