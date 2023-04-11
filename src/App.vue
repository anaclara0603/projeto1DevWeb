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
function confirma() {
  if (senha.value != confirmaSenha.value) {
    alert("senha incorreta")
  }
  else {
    enviar.value = !enviar.value
  }
}
</script>

<template>
  <div class="container">
    <div class="login">
      <h1>Login</h1>
      <label>Nome: </label>
      <input type="text" v-model="nome" placeholder="Nome" maxlength="20"/>
      <label>Email: </label>
      <input type="email" v-model="email" placeholder="Email" maxlength="20"/>
      <label>Data de Nascimento: </label>
      <input type="date" v-model="nascimento" placeholder="Data de Nascimento">
      <label>Seu endereço: </label>
      <input type="text" v-model="endereco" placeholder="Seu endereço" maxlength="20"/>
      <label>Sua cidade: </label>
      <input type="text" v-model="cidade" placeholder="cidade" maxlength="20"/>
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
      <input type="text" v-model="hobbie" placeholder="Hobbie" maxlength="20"/>
      <label>Linguagem que você programa: </label>
      <input type="text" v-model="linguagemProg" placeholder="Linguagem de Programação" maxlength="20" />
      <label>Biografia: </label>
      <input type="text" v-model="bio" placeholder="Biografia" maxlength="500"/>
      <label>Senha: </label>
      <input type="password" v-model="senha" placeholder="Senha" maxlength="20"/>
      <label>Confirme Senha: </label>
      <input type="password" v-model="confirmaSenha" placeholder="Confirme sua senha" maxlength="20">
      <button type="button" class="btn btn-danger" @click="confirma">enviar</button>
    </div>

    <div class="info" >
      <h1>Suas Informações</h1>
      <p class="text-danger">Nome: </p>
      <p>{{ nome }}</p>
      <p class="text-danger">Email: </p>
      <p>{{ email }}</p>
      <p class="text-danger">Senha: </p>
      <p>{{ senha }}</p>
      <p class="text-danger">Data de nascimento: </p>
      <p>{{ nascimento }}</p>
      <p class="text-danger">Estado: </p>
      <p>{{ estado }}</p>
      <p class="text-danger">Hobbie: </p>
      <p>{{ hobbie }}</p>
      <p class="text-danger">Linguagem de Programação: </p>
      {{ linguagemProg }}
      <p class="text-danger">Biografia: </p>
      <p class="text-bio">{{ bio }}</p>
    </div>
  </div>
</template>

<style scoped>

.text-bio {
  word-wrap: break-word;
  line-break: anywhere;
}
.container {
  display: flex;
  justify-content: space-around;
  width: 100%;
}

input {
  margin-top: 10px;
  margin-bottom: 10px;
  border-radius: 15px;
  width: 250px;
}

select {
  margin-top: 10px;
  margin-bottom: 10px;
  border-radius: 10px;
  width: 250px;
}

.login {
  margin-top: 40px;
  display: flex;
  flex-direction: column;
  background-color: rgb(0, 0, 0);
  border-radius: 15px;
  align-items: center;
  padding: 20px;
  width: 500px;
  margin-bottom: 20px;
}

.info {
  margin-top: 40px;
  display: grid;
  grid-template-columns: 1fr;
  background-color: rgb(0, 0, 0);
  border-radius: 15px;
  width: 500px;
  padding: 50px;
  color: white;
  margin-bottom: 20px;
}
h1{
  text-align: center;
  align-items: center;
  justify-content: center;
}


</style>
