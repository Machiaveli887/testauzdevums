<template>
  <div id="app"> 
    <nav-bar class="navbar"/>
    <div class="num">
      <p>Request #{{ reqNumber }}</p>
  </div>
    <div class="container">
      <sup-info class="item"></sup-info>
      <over-view />
      <map-view/>
    </div>
    <foo-ter></foo-ter>
</div>
 
  
</template>

<script>
import NavBar from './components/nav-bar.vue'
import FooTer from './components/footer.vue'
import SupInfo from './components/suplierInfo.vue'
import overView from './components/overView.vue'
import MapView from './components/map.vue'

export default {
  name: 'App',
  components: {
    NavBar,
    FooTer,
    SupInfo,
    overView,
    MapView,
  },

  data() {
    return {
      reqNumber: 779
    }
  }
}

 
</script>

<style scoped>
#app {
  margin: 0;
  padding: 0;
  font-family: Georgia, 'Times New Roman', Times, serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  
}
.container{
  display: flex;
  flex-direction: row;
  border: solid 1px grey;
}
.item{
  margin:0 100px 0 10px;
}

.num {
  position: relative;
  top: 50px;
  text-align: left;
  color: black;
}

</style>
