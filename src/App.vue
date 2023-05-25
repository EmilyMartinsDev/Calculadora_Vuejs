<script setup>
import { reactive } from 'vue';


const estado = reactive({
  primeiroNumero: '',
  segundoNumero:'',
  calculo:'',
  resultado:'',
});

function geraResultado(){
const {primeiroNumero, segundoNumero, calculo} = estado;

if(!primeiroNumero || !segundoNumero){
  return
}

switch (calculo){
  case 'multiplicar':
    return Number(primeiroNumero) * Number(segundoNumero);
  case 'dividir':
    return (Number(primeiroNumero) / Number(segundoNumero)).toFixed(2);
  case 'somar':
    return Number(primeiroNumero) + Number(segundoNumero);
  case 'subtrair':
    return Number(primeiroNumero) - Number(segundoNumero);
 
}

}

</script>

<template>

  <div class="container mt-5 bg-light">
  <header class="p-4 bg-dark text-white mb-5 text-center">
    <h1>Calculadora Aritmédica</h1>
  </header>
    <form action="">
      <div class="row">
        <div class="col-md-3">
          <input class="form-control" @change="(e)=>estado.primeiroNumero = e.target.value" type="number" placeholder="Primeiro numero">
        </div>
        <div class="col-md-3">
          <input class="form-control" @change="(e)=>estado.segundoNumero = e.target.value" type="number" placeholder="Segundo numero">
        </div>
        <div class="col-md-6">
          <select @change="(e)=>estado.calculo = e.target.value" class="form-control">
            <option value="multiplicar">multiplicar</option>
            <option value="dividir">dividir</option>
            <option value="somar">somar</option>
            <option value="subtrair">subtrair</option>
          </select>
        </div>
      </div>
    </form>
    <div  class="p-3 bg-success mt-5 display-4 text-center text-light">
      <span>Resultado:</span>
    <span>{{ geraResultado() }}</span>
    </div>
  </div>
</template>

<style scoped>
.form{
  background-color: #ccc;
}
.isInvalid{
  background-color: red;
}
</style>
