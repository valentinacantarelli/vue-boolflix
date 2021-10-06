<template>
  <div class="card">
      <h3>{{film.title || film.name}}</h3>
      <h4>{{film.original_title || film.original_name}}</h4>
      <lang-flag :iso="film.original_language" :squared="false"/>
      <div>{{film.vote_average}}</div>
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
    padding:10px 5px;
    text-align: center;
    border-radius:5px;

    h3{
      text-transform: uppercase;
      font-size:15px;
    }
    h4{
      font-weight: 300;
      font-size:14px;
    }
  }
</style>