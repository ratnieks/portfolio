<template>
  <div id="app">
    <button class="menu-btn" :class="[triggerMenu ? 'menu-btn--opened' : '']" @click="onMenuOpen()">
      <span class="menu-btn__top"></span>
      <span class="menu-btn__mid"></span>
      <span class="menu-btn__bottom"></span>
    </button>
    <HeaderComponent/>
    <transition name="fade">
      <MenuComponent @triggerMenu="onMenuClose()" v-if="triggerMenu"/>
    </transition>
    <AboutMeComponent/>
    <ProjectsComponent/>
  </div>
</template>
<script>
import HeaderComponent from './components/Header'
import MenuComponent from './components/Menu'
import AboutMeComponent from './components/AboutMe'
import ProjectsComponent from './components/Projects'
export default {
  name: 'app',
  data () {
    return {
      triggerMenu: false
    }
  },
  components: {
    HeaderComponent,
    MenuComponent,
    AboutMeComponent,
    ProjectsComponent
  },
  methods: {
    onMenuOpen () {
      this.triggerMenu = !this.triggerMenu
    },
    onMenuClose () {
      this.triggerMenu = !this.triggerMenu
    }
  },
  created () {
  }
}
</script>
<style scoped lang="stylus">
  .menu-btn
    position fixed
    display: flex
    flex-wrap: wrap
    align-items: center
    justify-content: center
    top 3rem
    right 3rem
    width 5rem
    height 5rem
    padding .7rem 1rem
    background-color black
    border none
    outline none
    z-index 3
    cursor pointer
    &__top, &__mid, &__bottom
      position relative
      width 100%
      height .3rem
      border-radius 1rem
      background-color white
      display inline-block
      margin .3rem 0
      transition: all .5s ease
    &__mid
      opacity 1
      ^[0]--opened &
        opacity 0
    &__top
      ^[0]--opened &
        transform rotate(45deg)
        top .8rem
    &__bottom
      ^[0]--opened &
        transform rotate(-45deg)
        bottom 1rem


  /* Menu  animation */
  .fade-enter-active, .fade-leave-active
    transition: opacity .5s
  .fade-enter, .fade-leave-to
    opacity: 0
</style>