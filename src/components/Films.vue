<template>
  <div class="containerMovie">
    <div class="rowMovie">
      <ul>
        <li v-for="(film,index) in research" :key="index" >
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
    props:["research"],
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

</style>