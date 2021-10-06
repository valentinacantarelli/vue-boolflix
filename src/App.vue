<template>
  <div id="app">
    <Header @search="searchContent"/>
    <main>
      <Films :research="films" :serieTv="series" />
    </main>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Films from './components/Films.vue'
import axios from 'axios';

export default {
  name: 'App',
  components: {
    Header,
    Films,
  },
  data(){
    return{
      films:[],
      series:[],
    }
  },
  methods:{
    searchContent(query){
      this.searchMovie(query);
      this.searchSerie(query)
    },
    searchMovie(query){
      axios.get('https://api.themoviedb.org/3/search/movie',{
          params:{
            api_key:'d32280abe309c24e5fa47ceb776eeba7',
            query: query,
            language:'it-IT'
          }
        })
        .then((res)=>{
          this.films=res.data.results;
        });
    },
    searchSerie(query){
      axios.get('https://api.themoviedb.org/3/search/tv',{
          params:{
            api_key:'d32280abe309c24e5fa47ceb776eeba7',
            query: query,
            language:'it-IT'
          }
        })
        .then((res)=>{
          this.series=res.data.results;
        });

    }
  }
}
</script>

<style lang="scss">
@import "./assets/style/common";
</style>