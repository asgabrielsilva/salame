<script setup>
import { ref } from 'vue'

const nome = ref('')
const email = ref('')
const senha = ref('')
const senhaConfirm = ref('')
const nascimento = ref()
const endereco = ref('')
const cidade = ref('')
const estado = ref([])
const hobbies = ref('')
const linguaProg = ref('')
const biografia = ref('')
const msgErro = ref("")

const mostrar = ref(false)

function valida() {
 if (senha.value === senhaConfirm.value) {
  msgErro.value = "";
  return true;
 }
 else {
  msgErro.value = "A confirmação da senha está incorreta.";
  return false;
 }
}

</script>

<template>
  <div class="mb-3">
    <form @submit.prevent="mostrar = valida()">
    <label for="nome" class="form-label">Nome</label>
    <input type="text" v-model="nome" class="form-control" minlength="3" required>
    <br>
  <label for="email" class="form-label">E-mail</label>
  <input type="email" v-model="email" class="form-control" required>
  <br>
  <label for="senha" class="form-label">Senha</label>
  <input type="password" v-model="senha" class="form-control" required>
  <br>
  <label for="senhaConfirm" class="form-label">Confirmar Senha</label>
  <input type="password" v-model="senhaConfirm" class="form-control" required>
  <br>
  <label for="nascimento" class="form-label">Data de Nascimento</label>
  <input type="date" v-model="nascimento" class="form-control" required>
  <br>
  <label for="endereco" class="form-label">Endereço</label>
  <input type="text" v-model="endereco" class="form-control" required>
  <br>
  <label for="cidade" class="form-label">Cidade</label>
  <input type="text" v-model="cidade" class="form-control" required>
  <br>
  <label for="estado" class="form-label">Estado</label>
  <select v-model="estado" required>
    <option value="Acre">AC</option>
    <option value="feminino">Feminino</option>
  </select>
  <br>
  <label for="hobbies" class="form-label">Hobbies</label>
  <input type="text" v-model="hobbies" class="form-control" required>
  <br>
  <label for="linguaProg" class="form-label">Linguagens de Programação</label>
  <input type="text" v-model="linguaProg" class="form-control" required>
<br>
  <label for="biografia" class="form-label">Biografia</label>
  <input type="text" v-model="biografia" class="form-control" required>
<br>
<input type="submit" value="Confirmar">

</form>
<p>{{ msgErro }}</p>
<div v-if="mostrar">
  <p>Nome: {{ nome }}</p>
  <p>E-mail: {{ email }}</p>
  <p>Senha: {{ senha }}</p>
  <p>Confirmação da Senha: {{ senhaConfirm }}</p>
  <p>Data de Nascimento: {{ nascimento }}</p>
  <p>Endereço: {{ endereco }}</p>
  <p>Cidade: {{ cidade }}</p>
  <p>Estado: {{ estado }}</p>
  <p>Hobbies: {{ hobbies }}</p>
  <p>Linguagens de Programação: {{ linguaProg }}</p>
  <p>Biografia: {{ biografia }}</p>
</div>
</div>

</template>

<style scoped>

</style>