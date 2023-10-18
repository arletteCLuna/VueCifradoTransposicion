<template>
    <div class="centered-content">
      
      <h1 class="subtitle">Cifrado de Transposición Escitala
      </h1><h1 class="subtitle">- - - Vue.Js y crypto-js - - -</h1>
      
      <div class="cipher-container">
        <div>
          <label for="inputText">Mensaje:</label>
          <input id="inputText" v-model="inputText" />
          <br><br>

        </div>
        <div>
          <label for="shift">Desplazar:</label>
          <input id="shift" type="number" v-model="shift" />
        </div>
        <button @click="encrypt" class="btn-cifrar">Cifrar</button>
        <button @click="decrypt" class="btn-descifrar">Descifrar</button>
        <div>
          <h2>Resultado:</h2>
          <p class="resultado">{{ result }}</p>
        </div>
        
      </div>
      <h1 class="title">Arlette Cruz Luna 7B</h1>
    </div>
  </template>
  
  <script>
  import CryptoJS from 'crypto-js';
  
  export default {
    data() {
      return {
        inputText: "",
        shift: 0,
        result: ""
      };
    },
    methods: {
      encrypt() {
        this.result = CryptoJS.AES.encrypt(this.inputText, this.shift.toString()).toString();
      },
      decrypt() {
        this.result = CryptoJS.AES.decrypt(this.result, this.shift.toString()).toString(CryptoJS.enc.Utf8);
      }
    }
  };
  </script>
  
  <style>
  .centered-content {
    text-align: center;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;
    background-color: #000000;
  }
  
  .title {
    color: #b700ff; 
  }
  
  .subtitle {
    color: #ffffff; 
  }
  
  .cipher-container {
    background-color: #f8f9fa; 
    padding: 20px;
    border-radius: 5px;
    font-size: 20px;
  }
  
  .btn-cifrar {
    background-color: #430a5a; 
    color: #fff;
    border: none;
    padding: 15px 25px;
    margin: 5px;
    border-radius: 5px;
  }
  input{
    padding: 20px;
    font-size: 20px;
  }
  .btn-descifrar {
    background-color: #dc3545;
    color: #fff;
    border: none;
    padding: 15px 25px;
    margin: 5px;
    border-radius: 5px;
  }
  
  .resultado {
    background-color: #ffffff; 
    padding: 10px;
    border-radius: 5px;
  }
  </style> 