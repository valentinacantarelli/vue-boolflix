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
  padding:15px 30px;
  background-color: rgba(0, 0, 0, 0.603);
  position:fixed;
  z-index: 1;

  h2{
    color:$mainColor;
  }
  input{
    margin:0 12px;
    border-radius: 5px;
    padding:4px 13px;
    background-color: $secondaryColor;
    border: none;
    color:white;
    &:focus{
      outline: none;
    }
  }
  button{
    background-color: $secondaryColor;
    color:white;
    cursor: pointer;
    
  }

}
</style>