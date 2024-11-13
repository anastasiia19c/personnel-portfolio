<template>
    <header class="banner">
      <div class="container">
        <h1> ! EN RECHERCHE DE STAGE EN DEVELOPPEMENT WEB !</h1>
      </div>
    </header>
</template>
  
  <script>
  export default {
    name: "Banner",
  };
  </script>
  
  <style scoped>
  .banner {
    position: fixed;  
    top: 0;         
    left: 0;
    height: 20px;
    width: 100%;     
    background-color: #FFBF00;; 
    color: black;     
    z-index: 1000;    
    display: flex;        
    justify-content: center;
    align-items: center;
    text-align: center;
    padding-top: 5px;
  }
  
  .container {
    display: flex;        
    justify-content: center;
    align-items: center;
    text-align: center;
  }
  
  h1 {
    font-size: 1rem;
    margin: 0;
    font-weight: bold;
    text-align: center;
  }
  
</style>
  