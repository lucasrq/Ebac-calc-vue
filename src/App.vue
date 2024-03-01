<script setup>
import { ref } from 'vue';

const numero1 = ref(0);
const numero2 = ref(0);
const operacao = ref('+');
const resultado = ref(0);

const calcular = () => {
  switch (operacao.value) {
    case '+':
      resultado.value = Number(numero1.value) + Number(numero2.value);
      break;
    case '-':
      resultado.value = Number(numero1.value) - Number(numero2.value);
      break;
    case '/':
      resultado.value = Number(numero1.value) / Number(numero2.value);
      break;
    case '*':
      resultado.value = Number(numero1.value) * Number(numero2.value);
      break;
    default:
      resultado.value = 0;
  }
}


</script>

<template>
  <div class="container top">
    <div class="container text-center">
      <div class="row">
        <div class="col">
          <h1>Calculadora</h1>
        </div>
      </div>
    </div>
    <div class="container text-center">
      <div class="row align-items-start">
        <div class="col">
          <input type="number" v-model="numero1" @input="calcular">
        </div>
        <div class="col mt-5">
          <select v-model="operacao" @change="calcular">
            <option value="+">+</option>
            <option value="-">-</option>
            <option value="/">/</option>
            <option value="*">*</option>
          </select>
        </div>
        <div class="col">
          <input type="number" v-model="numero2" @input="calcular">
        </div>
      </div>
    </div>

    <br>
    <hr>
    <p class="text-center">{{ resultado }}</p>
  </div>
</template>

<style scoped>
span {
  color: aqua;
}

sobre {
  display: flex;

}

.top {
  background-color: #cccccc66;
  height: 250px;
}

p {
  font-size: 2rem;
}

input {
  width: 50px;
}
</style>

