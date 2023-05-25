<script setup>
import { reactive } from 'vue';
import Form from './components/Form.vue';
import Resultado from './components/Resultado.vue';

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

  <div class="container p-5 mt-5 bg-light">
  <header class="p-4 bg-dark text-white mb-5 text-center">
    <h1>Calculadora Aritmédica</h1>
  </header>
  <Form 
    :valor-primeiro="(e)=> estado.primeiroNumero = e.target.value"
    :valor-segundo="(e)=> estado.segundoNumero = e.target.value"
    :valor-calculo="(e)=> estado.calculo = e.target.value"
    />
    
  <Resultado :gera-resultado="geraResultado()"/>
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
