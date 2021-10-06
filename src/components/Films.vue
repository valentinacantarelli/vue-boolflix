<template>
  <div class="containerMovie">
    <div class="rowMovie">
      <ul>
        <li v-for="(film,index) in research" :key="index" >
          <Card :film="film"/>  
        </li>
      </ul>
    </div>
    <div class="rowSerie">
      <ul>
        <li v-for="(film,index) in serie" :key="index" >
          <Card :film="film"/>  
        </li>
      </ul>
      
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
    props:["research","serie"],
    data(){
      return{
        searchFilm:""
      }
    },
    methods:{
      
}
}
</script>

<style lang="scss" scope>
@import '../assets/style/variables';

.containerMovie{
  background-color: rgb(17, 16, 16);
  color:white;
  
  .rowMovie{
    display:flex;
    width:90%;
    margin:auto;
    padding-top:20px;
    ul{
      display:flex;
      flex-wrap:wrap;
      li{
        margin:20px;
      }
    }
  }
}
</style>