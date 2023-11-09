<script setup>
import { reactive } from "vue";
import Formulario from "./components/form.vue";
import Cabecalho from './components/header.vue'
import Resultado from './components/resultado.vue'

const estado = reactive({
  input1: 0,
  input2: 0,
  operacao: "",
  resultado: 0
});


function operacoes()  {
        let operacao =  estado.operacao
        let resultado = 0 
        if(operacao === "+"){
             resultado = parseInt(estado.input1) + parseInt(estado.input2)
          return resultado
        } else if(operacao === "-"){
            resultado = parseInt(estado.input1) - parseInt(estado.input2)
          return resultado
        } else if(operacao === "*"){
           resultado = parseInt(estado.input1) * parseInt(estado.input2)
          return resultado
        } else if(operacao === "/"){
           resultado = parseInt(estado.input1) / parseInt(estado.input2)
          return resultado
        } else {
          alert("Insira os valores para calcular")
        }
        estado.resultado = resultado
        console.log(operacao)
      }
</script>

<template>
  <div class="container">
    <Cabecalho/>
    <Formulario :captura-input1="e => estado.input1 = e.target.value" :captura-input2="e => estado.input2 = e.target.value" :captura-select="(e) => estado.operacao = e.target.value"/>
    <Resultado :funcao-operacao="operacoes()"/>
  </div>
</template>

<style scoped>
.container {
  max-width: 1024px;
  width: 100%;
  margin: 0 auto;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  background-color: grey;
  padding: 20px;
  border-radius: 10px;
  color: white;
  font-family: sans-serif;
}
</style>
