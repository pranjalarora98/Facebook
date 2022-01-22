<template>
  <div id="app">
    <FaceBook/>
  </div>
</template>

<script>
import FaceBook from '@/components/FaceBook.vue'

export default {
  name: 'App',
  components: {
    FaceBook
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background: #f0f2f5;
}
</style>
