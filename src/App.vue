<template>
  <div id="app">
    <!-- nell'header richiamo con @select la funzione che gestisce la selezione dei generi musicali  -->
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


<style lang="scss" scoped>
@import "~bootstrap/scss/bootstrap";

</style>
