<template>
  <div>
     <div>{{research.title}}</div>
     <div>{{research.original_title}}</div> 
     <div>{{research.original_language}}</div>
     <div>{{research.vote_average}}</div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
    name:"Films",
    props:["research"],
    data(){
      return{
        searchFilm:""
      }
    },
    methods:{
      searchMovie(){
      axios.get('https://api.themoviedb.org/3/search/movie',{
          params:{
            api_key:'d32280abe309c24e5fa47ceb776eeba7',
            query:'searchText',
            language:'it-IT'
          }
        })
        .then((res)=>{
          this.searchFilm=res.data.response;
        });
  }
}
}
</script>

<style lang="scss" scope>

</style>