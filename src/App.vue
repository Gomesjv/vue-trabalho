<script setup>
import { ref } from 'vue';

const mostrar = ref(false)
const nome = ref("")
const email = ref("")
const idade = ref("")
</script>

<template>

<form>
  <div class="aaa">

<label>nome:</label>
<input type="text" v-model="nome"  placeholder="Digite seu nome"  minlength="3" maxlength="20" /> <hr>
<label>email:</label>
<input type="email" v-model="email"  placeholder="Digite seu email" minlength="3" maxlength="20" /><hr>
<label>idade:</label>
<input type="number" v-model="idade"  placeholder="Digite sua idade" minlength="1" maxlength="3" /><hr>



</div>
<div v-if="mostrar">
<p>seu nome cadastrado foi {{ nome }}</p>
<p>seu email cadastrado foi {{ email }}</p>
<p>sua idade cadastrada foi {{ idade }}</p>
</div>
<button type="submit" @click.prevent="mostrar = !mostrar">vdgsgs</button>

</form>
</template>


<style scoped>

</style>
