<template>
  <header>
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

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
