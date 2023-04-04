<script setup>
import { ref,computed } from 'vue';

const mostrar = ref(false)
const nome = ref("")
const email = ref("")
const idade = ref("")
const senha = ref("")
const SenhaConfirmacao = ref("")
const endereço = ref("")
const cidade = ref("")

function a(e){
  if(senha.value === SenhaConfirmacao.value)
  {
mostrar.value = true
  }
else{
mostrar.value = false
alert ('senha invalida')
}
}

const error = computed(() => {
  if(senha.value != SenhaConfirmacao.value){
    return 'senhas devem ser iguais'
  }else{
      return null
    }
  
} )

</script>

<template>

<form @submit.prevent="a">

<input   type="text" v-model="nome"  placeholder="Digite seu nome"  minlength="3" maxlength="20" required/>
<input  type="email" v-model="email"  placeholder="Digite seu email" minlength="3" maxlength="20" required/>
<input  type="number" v-model="idade"  placeholder="Digite sua idade" minlength="1" maxlength="3" required/>
<input type="password" v-model="senha"  placeholder="Digite sua senha" minlength="1" required/>
<input type="password" v-model="SenhaConfirmacao"  placeholder="confirme sua senha" minlength="1"  required/>
<input type="text" v-model="endereço"  placeholder="Digite seu endereço" required/>
<input type="text" v-model="cidade"  placeholder="Digite sua cidade" required/>

<select v-model="estado">
<label>

</label>

{{ error }}
<button type="submit">enviar</button>
</select>
  <label for="estado">Estado
  </label>
  <select v-model="estado">
    <option value="AC">Acre</option>
    <option value="AL">Alagoas</option>
    <option value="AP">Amapa</option>
    <option value="AM">Amazonas</option>
    <option value="BA">Bahia</option>
    <option value="CE">Ceara</option>
    <option value="DF">Distrito federal</option>
    <option value="ES">Esperito santo</option>
    <option value="GO">Goias</option>
    <option value="MA">Maranhao</option>
    <option value="MT">Mato Grosso</option>
    <option value="MS">Mato Grosso Do Sul</option>
    <option value="MG">Minas gerais</option>
    <option value="PA">Para</option>
    <option value="PB">Paraiba</option>
    <option value="PR">Parana</option>
    <option value="PE">Pernanbuco</option>
    <option value="PI">Piaui</option>
    <option value="RJ">Rio de janeiro</option>
    <option value="RN">Rondonia</option>
    <option value="RS">Riu grande do sul</option>
    <option value="RO">roraima</option>
    <option value="RR">roraima</option>
    <option value="SC">santa catarina</option>
    <option value="SP">sao paulo</option>
    <option value="SE">sergipe</option>
    <option value="TO">tocantis</option>
  </select>

</form>
<div v-if="mostrar">
<p>seu nome cadastrado foi {{ nome }}</p>
<p>seu email cadastrado foi {{ email }}</p>
<p>sua idade cadastrada foi {{ idade }}</p>
<p>sua senha cadastrada foi {{ senha }}</p>
<p>sua senha foi confimada como {{ SenhaConfirmacao }}</p>
<p>seu endereço foi cadastrado como  {{ endereço }}</p>
<p>sua cidade foi cadastrada como {{ cidade }}</p>
<p>sua senha foi confimada como {{ SenhaConfirmacao }}</p>
<p>sua senha foi confimada como {{ SenhaConfirmacao }}</p>
<p>sua senha foi confimada como {{ SenhaConfirmacao }}</p>
<p>sua senha foi confimada como {{ SenhaConfirmacao }}</p>
</div>
</template>


<style scoped>

</style>
