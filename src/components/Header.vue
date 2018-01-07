<template>
  <div class="header">
    <div class="header__content">
      <transition name="drop-top">
        <h1 v-show="loaded" class="header__content__title">Juris Ratnieks</h1>
      </transition>
      <br/>
      <transition name="drop-bottom">
        <p v-show="loaded" class="header__content__desc">this is my personal portfolio page</p>
      </transition>
    </div>
  </div>
</template>

<script>

export default {
  name: 'header-component',
  data () {
    return {
      loaded: false
    }
  },
  methods: {
    onMenuOpen () {
      this.showMenu = !this.showMenu
      this.$emit('triggerMenu')
    }
  },
  mounted () {
    setTimeout(() => {
      this.loaded = true
    }, 500)
  },
  created () {
    console.log(this)
  }
}
</script>
<style scoped lang="stylus">
  .header
    display: flex
    justify-content center
    align-items center
    position relative
    overflow hidden
    width 100%
    height 100vh
    background: linear-gradient( rgba(0, 0, 0, 0.1), rgba(0, 0, 0, 0.1) ), url("~/src/assets/img/header-bg.jpg")
    background-position: center
    background-size: cover
    &__content
      position relative
      color white
      text-align center
      &__title
        display inline-block
        text-transform: uppercase
        font-family: "OpenSans", sans-serif
        font-weight 700
        font-size: 4.2rem
        padding: 1rem 3.5rem
        border: .8rem solid white
        background-color: rgba(0,0,0, 0.2)
        box-shadow: rgba(0,0,0, .3) 0 0 0 100rem
        line-height 1.1
      &__desc
        display inline-block
        text-transform: uppercase
        letter-spacing: .4rem
        font-weight 300
        font-family: "OpenSans", sans-serif

</style>
