<template>
  <div class="card"  :style="{ backgroundImage: 'url(https://image.tmdb.org/t/p/w300'+film.poster_path+')'}" >
      <div class="infoFilm">
        <h3>{{film.title || film.name}}</h3>
        <h4>{{film.original_title || film.original_name}}</h4>
        <lang-flag :iso="film.original_language" :squared="false" />
        <div  class="votazione">
          <i class="fas fa-star" v-for="(stelle,indice) in votoInStelle" :key="indice"></i>
          <i class="far fa-star" v-for="(stelle,indice) in 5 - votoInStelle" :key="indice"></i>
        </div>
        
      </div>
  </div>
</template>

<script>
import LangFlag from 'vue-lang-code-flags'
export default {
    name:"Card",
    props:["film"],
    data(){
      return{
      }
    },
    components:{
      LangFlag
    },
    computed:{
      votoInStelle(){
        return Math.ceil(this.film.vote_average / 2)
      }
    }
}
</script>

<style lang="scss" scope>
@import '../assets/style/variables';
  .card{
    width:200px;
    height:290px;
    background-color:$secondaryColor;
    text-align: center;
    border-radius:3px;
    display:flex;
    background-position: center;
    background-size: cover;
    position:relative;
    background-repeat: no-repeat;
    
    .infoFilm{
      position:absolute;
      height: 100%;
      width:100%;
      top:0;
      left:0;
      padding:30px 10px;
      opacity:0;
      transition: 0.3s;

      &:hover  {
        background-color: rgba(29, 29, 29, 0.863);
        opacity: 1;
        cursor: pointer;
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
    .votazione{
      display:inline-block;
      color: goldenrod;
      padding:10px;
      font-size:17px;
    }
    .flag-icon{
      display:block;
      margin:0 auto;
      padding:14px;
      
    }
  }
</style>