<template>
  <header>
    <h2>BOOLFLIX</h2>
    <div>
      <input type="text" placeholder="cosa vuoi guardare oggi?" v-model="inputText">
      <button @click="$emit('search', inputText)">Cerca</button>
    </div>
  </header>
  
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
header{
  display: flex;
  width: 100%;
  justify-content: space-between;
  padding:10px 20px;
  background-color: black;

  h2{
    color:#de0913;
  }
  input{
    margin:0 10px;
    &:focus{
      outline: none;
    }
  }

}
</style>