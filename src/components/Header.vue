<template>
  <header>
    <div class="sx">
      <h2>BOOLFLIX</h2>
      <span>Home</span>
      <span>Serie Tv</span>
      <span>Film</span>
    </div>
    <div>
      <input type="text" placeholder="cosa vuoi guardare oggi?" v-model="inputText" @keyup.enter="$emit('search', inputText)">
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
@import url('https://fonts.googleapis.com/css2?family=Oswald:wght@300;500;700&display=swap');
header{
  display: flex;
  width: 100%;
  justify-content: space-between;
  padding:15px 30px;
  background-color: rgba(0, 0, 0, 0.788);
  position:fixed;
  z-index: 1;
  .sx{
    display:flex;
  }
  span{
    color:white;
    margin:0 8px 0 15px;
    line-height:37px;
    cursor: pointer;
  }

  h2{
    color:$mainColor;
    font-size: 25px;
    padding: 0 10px;
    box-shadow: 2px 2px 2px red;
    font-family: 'Oswald', sans-serif;
    margin-right:20px;
  }
  input{
    margin:5px 12px;
    border-radius: 5px;
    padding:4px 16px;
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