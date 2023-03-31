<script setup>
import { ref } from 'vue'

const nome = ref('')
const senha = ref('')
const email = ref('')

const enviar = ref(false)
</script>

<template>
  <div class="container">
    <div class="login">
    <label>Nome: </label>
    <input type = "text" v-model="nome" />
    <label>Senha</label>
    <input type="password" v-model="senha" />
    <label>Email: </label>
    <input type="email" v-model="email" />
  </div>
  <button @click="enviar = !enviar">Enviar</button>
  <div class="Info" v-if="enviar">
    <p>Suas Informações:</p>
    <p>Nome: {{ nome }}</p>
    <p>Email: {{ email }}</p>
    <p>Senha: {{ senha }}</p>
  </div>
  </div>
</template>

<style scoped>
  
</style>
