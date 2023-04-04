<script setup>
import { ref } from 'vue'

const nome = ref('')
const senha = ref('')
const email = ref('')
const confirmaSenha = ref('')
const nascimento = ref('')
const endereco = ref('')
const cidade = ref('')
const estado = ref('')
const hobbie = ref('')
const linguagemProg = ref('')
const bio = ref('')



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
    <input type = "text" v-model="nome" placeholder="Nome"/>
    <label>Email: </label>
    <input type="email" v-model="email" placeholder="Email"/>
    <label>Data de Nascimento: </label>
    <input type="date" v-model="nascimento" placeholder="Data de Nascimento">
    <label>Seu endereço: </label>
    <input type = "text" v-model="endereco" placeholder="Seu endereço"/>
    <label>Sua cidade: </label>
    <input type = "text" v-model="cidade" placeholder="cidade"/>
    <label>Selecione seu estado:</label>
    <select v-model="estado">
      <option value="AC">Acre</option>
      <option value="AL">Alagoas</option>
      <option value="AP">Amapa</option>
      <option value="AM">Amazonas</option>
      <option value="BA">Bahia</option>
      <option value="CE">Ceara</option>
      <option value="DF">Distrito Federal</option>
      <option value="ES">Espirito Santo</option>
      <option value="GO">Goiania</option>
      <option value="AC">Acre</option>
      <option value="MA">Maranhão</option>
      <option value="MT">Mato Grosso</option>
      <option value="MS">Mato Groso do Sul</option>
      <option value="MG">Minas Gerais</option>
      <option value="PA">Para</option>
      <option value="PB">Paraiba</option>
      <option value="PE">Pernanbuco</option>
      <option value="PI">Piauí</option>
      <option value="PR">Paraná</option>
      <option value="RJ">Rio de Janeiro</option>
      <option value="RN">Rio Grande do Norte</option>
      <option value="RS">Rio Grande do Sul</option>
      <option value="RO">Rondonia</option>
      <option value="RR">Roraima</option>
      <option value="SC">Santa Catarina</option>
      <option value="SP">São Paulo</option>
      <option value="SE">Sergipe</option>
      <option value="TO">Tocantins</option>
    </select>
    <label>Hobbie: </label>
    <input type = "text" v-model="hobbie" placeholder="Hobbie"/>
    <label>Linguagem que você programa: </label>
    <input type = "text" v-model="linguagemProg" placeholder="Linguagem de Programação"/>
    <label>Biografia: </label>
    <input type = "text" v-model="bio" placeholder="Biografia" maxlength="500"/>
    <label>Senha: </label>
    <input type="password" v-model="senha" placeholder="Senha"/>
    <label>Confirme Senha: </label>
    <input type="password" v-model="confirmaSenha" placeholder="Confirme sua senha">

  </div>
  <button @click="confirma">enviar</button>
  <div class="Info" v-if="enviar">
    <p>Suas Informações:</p>
    <p>Nome: {{ nome }}</p>
    <p>Email: {{ email }}</p>
    <p>Senha: {{ senha }}</p>
    <p>Data de nascimento: {{ nascimento }}</p>
    <p>Estado: {{ estado }}</p>
    <p>Hobbie: {{ hobbie }}</p>
    <p>Linguagem de Programação: {{ linguagemProg }}</p>
    <p>Biografia: {{ bio }}</p>
  </div>
  </div>
</template>

<style scoped>
  input{
    margin-top: 10px;
    margin-bottom: 10px;
    border-radius: 15px;
    width: 250px;
  }
  select{
    margin-top: 10px;
    margin-bottom: 10px;
    border-radius: 10px;
    width: 250px;
  }
  .login{
    display: grid;
    grid-template-rows: 1fr  ;
  }
</style>
