<template>
  <header>
    <h2>BOOLFLIX</h2>
    <div>
      <input type="text" placeholder="cosa vuoi guardare oggi?" v-model="inputText">
      <button @click="$emit('search', inputText)" class="btn">Cerca</button>
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
@import '../assets/style/variables';
header{
  display: flex;
  width: 100%;
  justify-content: space-between;
  padding:10px 20px;
  background-color: black;

  h2{
    color:$mainColor;
  }
  input{
    margin:0 12px;
    border-radius: 5px;
    padding:4px 13px;
    background-color: rgba(128, 128, 128, 0.315);
    border: none;
    color:white;
    &:focus{
      outline: none;
    }
  }
  button{
    background-color: rgba(128, 128, 128, 0.432);
    color:white;
    
  }

}
</style>