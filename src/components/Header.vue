<template>
  <div>
      <input type="text" placeholder="cosa vuoi guardare oggi?" v-model="inputText">
      <button @click="$emit('search', inputText)">Cerca</button>
  </div>
</template>

<script>
export default {
    name:"Header",
    data(){
      return{
        inputText:""
      } 
    },
}
</script>

<style lang="scss" scope>

</style>