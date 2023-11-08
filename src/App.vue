<script setup>
import { reactive } from "vue";


const estado = reactive({
  input1: 0,
  input2: 0,
  operacao: ""
});


function operacoes()  {
        let operacao =  estado.operacao
        if(operacao === "+"){
          const resultado = parseInt(estado.input1) + parseInt(estado.input2)
          return resultado
        } else if(operacao === "-"){
          const resultado = parseInt(estado.input1) - parseInt(estado.input2)
          return resultado
        } else if(operacao === "*"){
          const resultado = parseInt(estado.input1) * parseInt(estado.input2)
          return resultado
        } else if(operacao === "/"){
          const resultado = parseInt(estado.input1) / parseInt(estado.input2)
          return resultado
        } else {
          alert("Insira os valores para calcular")
        }

        console.log(operacao)
      }
</script>

<template>
  <div class="container">
    <h1>Calculadora</h1>
    <form>
      <input @keyup="(e) => estado.input1 = e.target.value" type="number" />
      <select @change="(e) => estado.operacao = e.target.value">
        <option selected></option>
        <option>+</option>
        <option >-</option>
        <option >*</option>
        <option >/</option>

      </select>
      <input @keyup="(e) => estado.input2 = e.target.value" type="number" />
    </form>
    <span>{{ operacoes() }}</span>
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
}

.container{
  background-color: grey;
  padding: 20px;
  border-radius: 10px;
  color: white;
  font-family: sans-serif;
}
h1 {
  text-align: center;
}

form{
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
}

input {
  height:  30px;
  width: 80px;
  font-size: 22px;
  color: white;
  background-color: transparent;
  border: none;
  border-bottom: 2px solid white;
  text-align: center;
  outline-color: grey;
}


span{
  display: block;
  margin-top: 20px;
  font-size: 22px;
  font-weight: bold;
  border: 3px dashed white;
  width: 220px;
  text-align: center;
  padding: 8px;
}

select{
  background-color: transparent;
  color: white;
  border: none;
  border-bottom: 2px solid white;
  height:  30px;
  padding: 2px;
  outline-color: grey;
  
}

select:focus{
  background-color: grey;
  border: 1px solid white;
}
</style>
