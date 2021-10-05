<template>
  <div id="app">
    <Header @search="searchMovie"/>
    <main>
      <Films/>
    </main>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Films from './components/Films.vue'

export default {
  name: 'App',
  components: {
    Header,
    Films,
  },
  data(){
    return{
      searchText:""
    }
    
  },
  methods:{
    searchMovie(txt){
      this.searchText = txt;
    }
  }
}
</script>

<style lang="scss">

</style>
