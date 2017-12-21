<template>
  <header class="header">
    <h1>Header</h1>
  </header>
</template>

<script>
export default {
  name: 'header',
  data () {
    return {
    }
  },
  created () {
    let array = ['1', '2', '3', '4', '5']
    let hello = 'Hello Juris'
    console.log(`${hello} and welcome back`)
    console.log(...array)
  }
}
</script>

<style scoped lang="stylus">
  .header
    display: inline-block
    position relative
    width 100%
    height 100vh
    background: linear-gradient( rgba(0, 0, 0, 0.4), rgba(0, 0, 0, 0.4) ), url("~/src/assets/img/header-bg.jpg");
    background-position: center
    background-size: cover
</style>
