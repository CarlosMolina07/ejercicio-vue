<script setup>
import { ref } from 'vue'

const solicitudes = ref(0)
const titulo = ref('Generador de solicitudes')

const incrementar = function () {
  solicitudes.value++
}

const decrementar = () => {
  if (solicitudes.value > 0) {
    solicitudes.value--
  }
}
</script>

<template>
  <h2>{{ titulo }}</h2>
  <div class="wrapper">
    <svg
      id="icon"
      xmlns="http://www.w3.org/2000/svg"
      fill="none"
      viewBox="0 0 24 24"
      stroke-width="1.5"
      stroke="currentColor"
      class="w-6 h-6"
    >
      <path
        stroke-linecap="round"
        stroke-linejoin="round"
        d="M17.982 18.725A7.488 7.488 0 0012 15.75a7.488 7.488 0 00-5.982 2.975m11.963 0a9 9 0 10-11.963 0m11.963 0A8.966 8.966 0 0112 21a8.966 8.966 0 01-5.982-2.275M15 9.75a3 3 0 11-6 0 3 3 0 016 0z"
      />
    </svg>
    <div id="globito" v-if="solicitudes > 0">
      {{ solicitudes }}
    </div>
  </div>
  <br />
  <span @click="decrementar" class="button"> - </span>

  <span @click="incrementar" class="button"> + </span>
  <br />
  <span v-show="solicitudes == 0">Nadie te agrega 😥</span>
  <br />
  <input type="text" v-model="titulo" />
</template>

<style scoped>
.button {
  margin: 4px;
  display: inline-block;
  background-color: gray;
  color: white;
  width: 32px;
  height: 32px;
  text-align: center;
  border-radius: 6px;
}

.button:hover {
  background-color: blanchedalmond;
  color: black;
  cursor: pointer;
}
.wrapper {
  /*background-color: orange;*/
  display: inline-block;
  position: relative;
}

#globito {
  background-color: red;
  width: 24px;
  height: 24px;
  font-weight: bold;
  text-align: center;
  border-radius: 100%;
  position: absolute;
  top: -12px;
  right: -12px;
}

#icon {
  width: 42px;
  height: 42px;
}
</style>
