<template>
  <div class="menu">
    <transition name="drop-top">
      <ul class="menu__list" v-show="loaded">
        <li class="menu__list__item"
            v-scroll-to="{ element: '#about', easing: 'ease-out', duration: 700}"
            @click="onCloseMenu()">
          About me
        </li>
        <li class="menu__list__item"
            v-scroll-to="{ element: '#portfolio', easing: 'ease-out', duration: 700}"
            @click="onCloseMenu()">
          Portfolio
        </li>
        <li class="menu__list__item">My Jobs</li>
        <li class="menu__list__item">Skills</li>
      </ul>
    </transition>
  </div>
</template>

<script>
  export default {
    name: 'menu-component',
    data () {
      return {
        loaded: false
      }
    },
    methods: {
      onCloseMenu () {
        this.$emit('triggerMenu')
      }
    },
    mounted () {
      this.loaded = !this.loaded
    }
  }
</script>

<style scoped lang="stylus">
  .menu
    position: fixed
    display flex
    justify-content center
    align-items center
    width: 100%
    height: 100vh
    top: 0
    z-index: 2
    background-color: rgba(0,0,0, .93)
    &__list
      padding 0
      margin 0
      list-style none
      width: 100%
      text-align: center
      &__item
        width: 100%
        text-align: center
        color: #c5c3c2
        letter-spacing: 0.2rem
        text-decoration: none
        font-family: "OpenSans", sans-serif
        font-weight: 400
        text-transform: uppercase
        padding: 2rem 0
        cursor: pointer
        transition all .7s
        &:hover
          color: #c71059
          letter-spacing: .6rem
</style>