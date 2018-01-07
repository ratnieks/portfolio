<template>
  <section class="about" id="about">
    <transition name="drop-bottom">
      <div v-show="loaded" class="about__title-block">
        <h2 class="title">Summary</h2>
        <p class="description">INFORMATION ABOUT MY EXPERIENCE AND KNOWLEDGE</p>
      </div>
    </transition>
    <div class="about__content">
      <div class="about__content__block about__content__block--right">
        <transition name="drop-left">
          <h1 v-show="loaded" class="about__content__title">Jobs</h1>
        </transition>
        <transition-group name="bounce-left">
          <div key="ms-idi" v-show="loaded">
            <div  class="about__content__info">
              <div class="about__content__info__year">2015</div>
              <h4 class="about__content__info__title"><span>"MS-IDI"</span> Web developer</h4>
              <p class="about__content__info__description">
                Curabitur ullamcorper ultricies nisi. Curabitur a felis in nunc fringilla tristique.
                Quisque libero metus, condimentum nec, tempor a, commodo mollis, magna. Suspendisse pulvinar,
                augue ac venenatis condimentum, sem libero volutpat nibh, nec pellentesque velit pede quis nunc. Nunc nec neque.
              </p>
            </div>
            <div  class="about__content__info">
              <div class="about__content__info__year">2015</div>
              <h4 class="about__content__info__title"><span>"MS-IDI"</span> Web developer</h4>
              <p class="about__content__info__description">
                Curabitur ullamcorper ultricies nisi. Curabitur a felis in nunc fringilla tristique.
                Quisque libero metus, condimentum nec, tempor a, commodo mollis, magna. Suspendisse pulvinar,
                augue ac venenatis condimentum, sem libero volutpat nibh, nec pellentesque velit pede quis nunc. Nunc nec neque.
              </p>
            </div>
            <div  class="about__content__info">
              <div class="about__content__info__year">2015</div>
              <h4 class="about__content__info__title"><span>"MS-IDI"</span> Web developer</h4>
              <p class="about__content__info__description">
                Curabitur ullamcorper ultricies nisi. Curabitur a felis in nunc fringilla tristique.
                Quisque libero metus, condimentum nec, tempor a, commodo mollis, magna. Suspendisse pulvinar,
                augue ac venenatis condimentum, sem libero volutpat nibh, nec pellentesque velit pede quis nunc. Nunc nec neque.
              </p>
            </div>
          </div>
        </transition-group>
      </div>
      <div class="about__content__split"></div>
      <div class="about__content__block about__content__block--left">
        <transition name="drop-right">
          <h1 v-show="loaded" class="about__content__title">Study</h1>
        </transition>
        <transition-group name="bounce-right">
          <div key="auto" v-show="loaded">
            <div  class="about__content__info">
              <div class="about__content__info__year">2014-2015</div>
              <h4 class="about__content__info__title">Schoolboy <span>"Autoskola FORMULA"</span></h4>
              <p class="about__content__info__description">
                Curabitur ullamcorper ultricies nisi. Curabitur a felis in nunc fringilla tristique.
                Quisque libero metus, condimentum nec, tempor a, commodo mollis, magna. Suspendisse pulvinar,
                augue ac venenatis condimentum, sem libero volutpat nibh, nec pellentesque velit pede quis nunc. Nunc nec neque.
              </p>
            </div>
            <div  class="about__content__info">
              <div class="about__content__info__year">2014-2015</div>
              <h4 class="about__content__info__title">Schoolboy <span>"Autoskola FORMULA"</span></h4>
              <p class="about__content__info__description">
                Curabitur ullamcorper ultricies nisi. Curabitur a felis in nunc fringilla tristique.
                Quisque libero metus, condimentum nec, tempor a, commodo mollis, magna. Suspendisse pulvinar,
                augue ac venenatis condimentum, sem libero volutpat nibh, nec pellentesque velit pede quis nunc. Nunc nec neque.
              </p>
            </div>
          </div>
        </transition-group>
      </div>
    </div>
  </section>
</template>

<script>
  const inViewport = require('vue-in-viewport-mixin')
  export default {
    name: 'about-component',
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
  .about
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
        background-color black
    &__content
      position relative
      display flex
      justify-content center
      margin-top 5rem
      &__split
        position relative
        width .2rem
        background-color #c1c1c1
      &__block
        position relative
        width 50%
        padding 4rem 1.5rem 0 1.5rem
        &--right
          text-align right
        &--left
          text-align left
      &__title
        font-weight 600
        font-size 3rem
        text-transform uppercase
        color purple
        margin-bottom 6rem
      &__info
        width 100%
        max-width 40rem
        position relative
        display inline-block
        &__year
          display: inline-block
          padding: 0 1.5rem
          font-weight 600
          margin-bottom: 2rem
          background-color: #ff307c
          font-size 1.4rem
          color: white
        &__title
          text-transform: uppercase
          font-weight: bold
          font-size: 1.4rem
          letter-spacing: .2rem
          span
            font-style italic
            font-weight 400
        &__description
          font-style: italic
          color: #7d807e
          margin-bottom: 3rem
          padding: 0
</style>