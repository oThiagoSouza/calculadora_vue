<script setup>

</script>

<template>
  <div class="container">
    <header class="pb-3 pt-3 mb-5 mt-5 bg-light rounded-4" >
      <h1 class="text-center">
        Calculadora com VueJS
      </h1>
    </header>
    <div class="row">
      <div class="col d-flex">
        <input type="number" class="num1 form-control me-2">
        <input type="number" class="num2 form-control me-2 ">
        <button type="button" class="me-2 btn btn-primary">Calcular</button>
        <select id="operacao" class="text-center form-control">
          <option value="Adição">Adição</option>
          <option value="Adição">Subtração</option>
          <option value="Adição">Multiplicação</option>
          <option value="Adição">Divisão</option>
        </select>
      </div>
    </div>
    <div class="row">
      <div class="col">
        <span>
            
        </span>
      </div>
    </div>
  </div>
</template>

<style scoped>
  .num1,.num2{
    max-width: 150px;
  }
  .btn {
    max-width: 150px;
    width: 100%;
  }
  
  #operacao {
    width: 150px;
  }
</style>
