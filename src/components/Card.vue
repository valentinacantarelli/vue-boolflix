<template>
  <div class="card">
      <h3>{{film.title}}</h3>
      <h4>{{film.original_title}}</h4>
      <div>{{film.original_language}}</div>
      <div>{{film.vote_average}}</div>
  </div>
</template>

<script>
export default {
    name:"Card",
    props:["film"]
}
</script>

<style lang="scss" scope>

</style>