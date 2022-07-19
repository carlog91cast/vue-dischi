<template>
  <div id="app">
    <SongHeader/>
    <SongMain/>
  </div>
</template>

<script>
import SongHeader from './components/SongHeader.vue'
import SongMain from './components/SongMain.vue'

export default {
  name: 'App',
  components: {
    SongHeader,
    SongMain,
  }
}
</script>


<style lang="scss">
@import "~bootstrap/scss/bootstrap";

</style>
