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
    alert('senha e confirmação senha não conferem')
    return false;
  }
  else {
    return true;
  }
}
</script>

<template>
  <div class="container">

    <div class="info" v-if="enviar">
      <h1>Suas Informações</h1>
      <p class="rosa">Nome: </p>
      <p class="a">{{ nome }}</p>
      <p class="rosa">Email: </p>
      <p class="a">{{ email }}</p>
      <p class="rosa">Senha: </p>
      <p class="a">{{ senha }}</p>
      <p class="rosa">Data de nascimento: </p>
      <p class="a">{{ nascimento }}</p>
      <p class="rosa">Estado: </p>
      <p class="a">{{ estado }}</p>
      <p class="rosa">Hobbie: </p>
      <p class="a">{{ hobbie }}</p>
      <p class="rosa">Linguagem de Programação: </p>
      <p class="a">{{ linguagemProg }}</p>
      <p class="rosa">Biografia: </p>
      <p class="a">{{ bio }}</p>
    </div>

    <div v-else>
      <form @submit.prevent="enviar = confirma()">

        <div class="login">
          <h1>Login</h1>
          <label>Nome: </label>
          <input type="text" v-model="nome" placeholder="Nome" minlength="3" maxlength="20" required>
          <label>Email: </label>
          <input type="email" v-model="email" placeholder="Email" minlength="3" maxlength="20" required />
          <label>Data de Nascimento: </label>
          <input type="date" v-model="nascimento" placeholder="Data de Nascimento">
          <label>Seu endereço: </label>
          <input type="text" v-model="endereco" placeholder="Seu endereço" minlength="3" maxlength="20" required>
          <label>Sua cidade: </label>
          <input type="text" v-model="cidade" placeholder="cidade" minlength="3" maxlength="20" required />
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
          <input type="text" v-model="hobbie" placeholder="Hobbie" minlength="3" maxlength="20" required />
          <label>Linguagem que você programa: </label>
          <input type="text" v-model="linguagemProg" placeholder="Linguagem de Programação" minlength="3" maxlength="20"
            required />
          <label>Biografia: </label>
          <input type="text" v-model="bio" placeholder="Biografia" maxlength="500" />
          <label>Senha: </label>
          <input type="password" v-model="senha" placeholder="Senha" minlength="3" maxlength="20" required>
          <label>Confirme Senha: </label>
          <input type="password" v-model="confirmaSenha" placeholder="Confirme sua senha" minlength="3" maxlength="20"
            required>
          <input type="submit" value="Enviar" class="btn">
        </div>

      </form>
    </div>

  </div>
</template>

<style scoped>
.btn {
  background-color: rgb(211, 55, 159);
  color: white;
  border: 4px solid rgb(248, 151, 216);
  width: 240px;
  border-radius: 15px;
}

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
  border: 4px solid rgb(248, 151, 216);
  padding-left: 15px;
}

input:focus {

  outline: none;
}

select {
  margin-top: 10px;
  margin-bottom: 10px;
  border-radius: 10px;
  width: 250px;
  border: 4px solid rgb(248, 151, 216);
  padding-left: 15px;
}

.login {
  margin-top: 40px;
  display: flex;
  flex-direction: column;
  background-color: rgb(211, 55, 159);
  border-radius: 15px;
  align-items: center;
  padding: 20px;
  width: 500px;
  margin-bottom: 20px;
}

.rosa {
  color: rgb(247, 164, 219);
}

.info {
  margin-top: 40px;
  display: grid;
  grid-template-columns: 1fr;
  background-color: rgb(211, 55, 159);
  border-radius: 15px;
  width: 500px;
  padding: 50px;
  color: white;
  margin-bottom: 20px;
}

h1 {
  text-align: center;
  align-items: center;
  justify-content: center;
  color: rgb(255, 255, 255);
  text-shadow: -2px 1px 0px rgb(248, 151, 216);
}

.a {
  color: antiquewhite;
}
</style>
