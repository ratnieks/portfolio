<template>
  <section class="projects" id="portfolio">
    <transition name="drop-bottom">
      <div v-show="loaded" class="projects__title-block">
        <h2 class="title title--light">Portfolio</h2>
        <p class="description description--light">INFORMATION ABOUT MY Projects</p>
      </div>
    </transition>
    <div class="projects__gallery">
      <div class="projects__gallery__item">sdsd</div>
      <div class="projects__gallery__item">sdsd</div>
      <div class="projects__gallery__item">sdsd</div>
      <div class="projects__gallery__item">sdsd</div>
      <div class="projects__gallery__item">sdsdsd</div>
    </div>
  </section>
</template>

<script>
  const inViewport = require('vue-in-viewport-mixin')
  export default {
    name: 'projects-component',
    data () {
      return {
        loaded: false
      }
    },
    watch: {
      'inViewport.now': function (visible) {
        if (visible) {
          this.loaded = true
        }
      }
    },
    mixins: [ inViewport ]
  }
</script>

<style scoped lang="stylus">
  .projects
    background-color: #222222
    display flex
    flex-direction column
    align-items center
    &__title-block
      display: flex
      flex-direction: column
      align-items: center
      &:after
        content ''
        position relative
        display inline-block
        width 10%
        height .1rem
        background-color: #7f7f7f
    &__gallery
      position relative
      max-width 99.2rem
      width 100%
      display flex
      flex-wrap wrap
      &__item
        position relative
        width 25%
        height 20rem
        background-color white
</style>