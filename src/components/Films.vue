<template>
  <div class="containerMovie">
    <div class="title"><h2>Ecco i film consigliati per te</h2></div>
    <div class="rowMovie" v-if="research.length>0">
      <div class="sezione">
        <ul>
          <li v-for="(film,index) in research" :key="index" >
            <Card :film="film"/>  
          </li>
        </ul>
      </div>
    </div>
    <div class="title"><h2>Ecco le serie consigliate per te</h2></div>
    <div class="rowSerie" v-if="serieTv.length>0">
      <div class="sezione">
        <ul>
          <li v-for="(film,index) in serieTv" :key="index" >
            <Card :film="film"/>  
          </li>
      </ul>
      </div>      
    </div>
  </div>
</template>

<script>
import Card from './Card.vue'
export default {
    name:"Films",
    components:{
      Card
    },
    props:["research","serieTv"],
    data(){
      return{
        searchFilm:""
      }
    },
}
</script>

<style lang="scss" scope>
@import '../assets/style/variables';

.containerMovie{
  background-color: rgb(17, 16, 16);
  color:white;
  height:100%;
  padding-top:70px;
  
  .title{
    margin:20px;
  }
  .rowMovie, .rowSerie{
    width:96%;
    margin:auto;
    padding-top:20px;
    display: flex;
    
    .sezione{
      display:flex;
      justify-items: space-between;
      
      ul{
      display:flex;
      flex-wrap:wrap;
      li{
        margin:20px 18px ;
      }
     }
    }
  }
}
</style>