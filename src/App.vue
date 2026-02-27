<script setup>
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <div class="container">
    <h1>Projeto Calculadora</h1>

    <div class="form">
      <label>Primeiro número:</label>
      <input type="number" v-model="value1"/>
      <label>Segundo número:</label>
      <input type="number" v-model="value2"/>

      <button @click="calcSum">Calcular Soma</button>
      <button @click="calcSub">Calcular Subtração</button>
      <button @click="calcMult">Calcular Multiplicação</button>
      <button @click="calcDiv">Calcular Divisão</button>
      <button @click="calcVel">Calcular Velocidade (D/T)</button>

      <div class="result">
        <h2>Resultado: {{ result }}</h2>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      value1: 0,
      value2: 0,
      result: 0
    };
  },
  methods: {
    calcSum() {
      this.result = parseFloat(this.value1) + parseFloat(this.value2);
    },
    calcSub() {
      this.result = parseFloat(this.value1) - parseFloat(this.value2);
    },
    calcMult() {
      this.result = parseFloat(this.value1) * parseFloat(this.value2);
    },
    calcDiv() {
      if (this.value2 != 0) {
        this.result = parseFloat(this.value1) / parseFloat(this.value2);
      } else {
        this.result = 'Erro: Divisão por zero';
      }
    },
    calcVel() {
      if (this.value2 != 0) {
        this.result = parseFloat(this.value1) / parseFloat(this.value2);
      } else {
        this.result = 'Erro: Divisão por zero';
      }
    }
  }
};
</script>

<style>
.container {
  text-align: center;
  margin-top: 50px;
  font-family: Arial, sans-serif;
}

.form {
  display: flex;
  flex-direction: column;
  width: 300px;
  margin: auto;
  gap: 10px;
}

input {
  padding: 8px;
  font-size: 16px;
}

button {
  padding: 10px;
  background-color: #42b883;
  color: white;
  border: none;
  cursor: pointer;
  font-size: 16px;
}

button:hover {
  background-color: #2f8f6f;
}

.result {
  margin-top: 20px;
  font-weight: bold;
}

</style>
