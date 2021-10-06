<template>
  <div class="card" :style="{ backgroundImage: 'url(https://image.tmdb.org/t/p/w300'+film.poster_path+')'}" >
      <div class="infoFilm">
        <h3>{{film.title || film.name}}</h3>
        <h4>{{film.original_title || film.original_name}}</h4>
        <lang-flag :iso="film.original_language" :squared="false"/>
        <div>{{film.vote_average}}</div>
      </div>
  </div>
</template>

<script>
import LangFlag from 'vue-lang-code-flags'
export default {
    name:"Card",
    props:["film"],
    components:{
      LangFlag
    }
}
</script>

<style lang="scss" scope>
@import '../assets/style/variables';
  .card{
    width:150px;
    height:220px;
    background-color:$secondaryColor;
    padding:20px 5px;
    text-align: center;
    border-radius:5px;
    display:flex;
    background-position: center;
    background-size: cover;
    position:relative;
    &:hover{
        opacity: 0.5;
    .infoFilm{
      position:absolute;
      width:150px;
      height:220px;
      
      
      }
      
    }
    h3{
      text-transform: uppercase;
      font-size:15px;
      padding-bottom:5px;
      
    }
    h4{
      font-weight: 300;
      font-size:14px;
      padding-bottom:5px;
    }
  }
</style>