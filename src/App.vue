<script setup>
import { reactive } from 'vue';


const calculadora = reactive({
  resultado: 0,
  num1: 0,
  num2: 0,
  operation: 'sum',
});

function calculadora1(evt) {
  
  calculadora.num1 = parseInt(evt);

  aritimetic(calculadora.operation);
}


function calculadora2(evt) {

  calculadora.num2 = parseInt(evt);

  aritimetic(calculadora.operation);

}

function aritimetic(evt) {
  calculadora.operation = evt;

  if (calculadora.operation == 'sum') {
    sum(calculadora.num1, calculadora.num2);
  } else if (calculadora.operation == 'substract') {
    substract(calculadora.num1, calculadora.num2);
  } else if (calculadora.operation == 'multiply') {
    multiply(calculadora.num1, calculadora.num2);
  } else if (calculadora.operation == 'divide') {
    divide(calculadora.num1, calculadora.num2);
  }

}
function sum(num1, num2) {
  calculadora.resultado = num1 + num2;
}

function substract(num1, num2) {
  calculadora.resultado = num1 - num2;
}

function multiply(num1, num2) {
  calculadora.resultado = num1 * num2;
}

function divide(num1, num2) {
  calculadora.resultado = num1 / num2;
}
</script>

<template>
  <div id="calculadora">
    <h1>Calculadora</h1>
    <input type="number" id="number1" name="number1" @keyup="calculadora1($event.target.value)">

    <select @change="aritimetic($event.target.value)">
      <option selected value="sum">+</option>
      <option value="substract">-</option>
      <option value="multiply">*</option>
      <option value="divide">/</option>
    </select>

    <input type="number" id="number2" name="number2" @keyup="calculadora2($event.target.value)">

    <h3>= {{ calculadora.resultado }}</h3>
   
  </div>
</template>

<style scoped>
  * {
    font-family: sans-serif;
  }

  h1 {
    display: flex;
    justify-content: center;
  }
  #calculadora {
    display: flex;
    justify-content: center;
    flex-direction: column;
    align-items: center;
    padding: 100px;
  }

  input, select {
    display: flex;
    flex-direction: column;
    align-items: center;
    max-width: 350px;
  }

  h3 {
    margin-top: 30px;
  }
</style>