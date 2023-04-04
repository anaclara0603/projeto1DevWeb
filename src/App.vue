<script setup>
import { ref } from 'vue'

const nome = ref('')
const senha = ref('')
const email = ref('')
const confirmaSenha = ref('')

const enviar = ref(false)
function confirma(){
  if(senha.value != confirmaSenha.value){
    alert("senha incorreta")
  }
  else{
    enviar.value = !enviar.value
  }
}
</script>

<template>
  <div class="container">
    <div class="login">
    <label>Nome: </label>
    <input type = "text" v-model="nome" />
    <label>Senha</label>
    <input type="password" v-model="senha" />
    <label>Confirma senha:</label>
    <input type="password" v-model="confirmaSenha">
    <label>Email: </label>
    <input type="email" v-model="email" />
  </div>
  <button @click="confirma">enviar</button>
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
