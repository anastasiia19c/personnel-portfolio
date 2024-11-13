<template>
    <header class="banner">
      <div class="container">
        <h1>! A LA RECHERCHE D'UN STAGE EN DEVELOPPEMENT WEB !</h1>
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
  }
  
  h1 {
    font-size: 1.2rem;  
    margin: 0;
    font-weight: bold;
    text-align: center;
    line-height: 1.2;  
  }
  
  @media (max-width: 768px) {
    .banner {
      height: auto;      
      padding: 10px 0;   
    }
  
    h1 {
      font-size: 1rem;   
    }
  }
  
  @media (max-width: 480px) {
    .banner {
      padding: 3px 0;  
    }
  
    h1 {
      font-size: 0.7rem;  
    }
  }
  </style>
  