<template>
  <div id="app">
    <RickAndMorty/>
  </div>
</template>

<script>
import RickAndMorty from './components/rickAndMorty.vue';

export default {
  name:'App',
  components:{
    RickAndMorty
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
}
div{
  margin: 0;
  padding: 0;

}
</style>
