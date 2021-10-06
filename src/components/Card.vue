<template>
  <div class="card">
      <h3>{{film.title}}</h3>
      <h4>{{film.original_title}}</h4>
      <div>{{film.original_language}}</div>
      <lang-flag :iso="film.original_language" squared="false"/>
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
  .card{
    width:150px;
    height:250px;
  }
</style>