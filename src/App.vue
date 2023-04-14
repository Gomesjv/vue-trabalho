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
const biografia = ref("")
const programacao = ref("")
const estado = ref("")

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
  <div class="container">
    <div class="resultado" v-if="mostrar">
<h1>Seu cadastro</h1>

<p>seu nome cadastrado foi {{ nome }}</p>
<p>seu email cadastrado foi {{ email }}</p>
<p>sua idade cadastrada foi {{ idade }}</p>
<p>sua senha cadastrada foi {{ senha }}</p>
<p>sua senha foi confimada como {{ SenhaConfirmacao }}</p>
<p>seu endereço foi cadastrado como  {{ endereço }}</p>
<p>sua cidade foi cadastrado como {{ cidade }}</p>
<p>seu estado foi cadastrado como {{ estado }}</p>
<p>seu hobie foi confimada como {{ hobie }}</p>
<p>suas linguagens de programaçoes confimada como {{ programacao }}</p>
<p>sua biografia foi confimada como {{ biografia }}</p>

</div>

<form class="login" @submit.prevent="a" v-else>

  <h1>Tela de login</h1>

<input   type="text" v-model="nome"  placeholder="Digite seu nome"  minlength="3" maxlength="20" required/>
<input  type="email" v-model="email"  placeholder="Digite seu email" minlength="3" maxlength="20" required/>
<input  type="date" v-model="idade"  minlength="1" maxlength="3" required/>
<input type="password" v-model="senha"  placeholder="Digite sua senha" minlength="1" required/>
<input type="password" v-model="SenhaConfirmacao"  placeholder="confirme sua senha" minlength="1"  required/>
<input type="text" v-model="endereço"  placeholder="Digite seu endereço" required/>
<input type="text" v-model="cidade"  placeholder="Digite sua cidade" required/>

<input type="text" v-model="hobie"  placeholder="Digite seu hobie" required/>
<input type="text" v-model="programcao"  placeholder="Digite suas linguagens de programção" required/>
<textarea v-model="biografia" id="" cols="10" rows="10" required/>

<select v-model="estado" required>


{{ error }}


  <label for="estado">
  </label>
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
  <button type="submit">enviar</button>

</form>

  </div>
  
</template>


<style scoped>

.container{
  height: 100vh;
  display: flex;
  justify-content: center;
}
.login{
display: grid;
grid-template-columns: 1fr;
background-color: blue;
height: 850px;
width:400px;
border-radius: 20px;
justify-items: center;
}
input{
  border-radius: 10px;
  border-color: black ;
  width: 200px;
  height: 30px;
  margin: 10px;
}
::placeholder{
  color: black;
}
button{
  height: 30px;
  width: 210px;
  border-radius: 10px;
 margin: 10px;
}
#login{
  background-color: black
}
h1{
  text-align: center;
  color: black;
}
textarea{
width: 200px;
height: 100px;
border-radius: 10px;
}
select{
  width: 210px;

  border-radius: 10px;
}
.resultado{
padding: 10px;
  background-color: blue;
  width:400px;
  height: 500px;
border-radius: 20px;
color: black;
}
</style>
