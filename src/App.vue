<script setup>
import { ref } from 'vue';

const rawHtml = '<span style="color: red">Este é um texto em vermelho</span>';
const contador = ref(0)
const numero = 1;
  const ok = true
  const mensagem = 'programar';

  function inverter(texto) {
    return texto.split('');
  }

 function encrementarContador(){
     contador.value++
 }
 function decrementarContador(){
  if(contador.value >= 0){
     contador.value--
  }
 }
 function resetContador(){
     contador.value = 0
 }
  const url = 'https://vuejs.org/';

  function mostrarAlerta () {
    alert('Botão clicado!');
  };

  const nomeAtributo = 'href';
  const nomeEvento = 'click';

  const nome = 'Guilherme'
    const idade = 17

    function inverterJoao(texto) {
        return texto.split('').reverse().join('')
    }

    function saudacao() {
        return `Olá, ${nome}!`
    }
</script>

<template>
 <div> 
<button id="encrementar" @click="encrementarContador">+</button>
<button id="decrementar" @click="decrementarContador">-</button>
<button id="reset" @click="resetContador">Resetar</button>
<br>
<p>Valor do contador é = {{ contador }}</p>
<p>Usando v-html: <span v-html="rawHtml"></span></p>

</div>
<div v-if="contador > 10 " class="maior10">
  <p>O número do contador é maior que dez!</p>
</div>
<div v-if="contador < 10" class="menor10"> 
  <p>O número é menor que dez!</p>
</div>
<div v-if="contador == 10" class="dez">
  O número do contador é dez!
</div>

  <p>{{ numero * 100 }}</p>
  <p>{{ ok ? 'Sim' : 'Não' }}</p>
  <p>{{mensagem.split('').reverse().join('') }}</p>
  <p>{{ inverter(mensagem) }}</p>
  <div v-if="ok">Mostrar</div>
  
  <a v-bind:href="url">Mais informações1...</a>
  <a :href="url">Mais informações2...</a>

  <button v-on:click="mostrarAlerta">Clique aqui3</button>
  <button @click="mostrarAlerta">Clique aqui3</button>

  <a v-bind:[nomeAtributo]="url">Mais informações3...</a>

  <button v-on:[nomeEvento]="mostrarAlerta">Clique aqui3</button>

  <button v-on:click.stop="mostrarAlerta">Clique aqui4</button>

  <div class="info">
        <h1>Exemplo 1 - Mostrando informações na tela</h1>
        <p>Nome: {{ nome }} </p>
        <p>Idade: {{ idade }}  anos</p>
        <hr />
        <p>Para completar 50 anos faltam: {{ 50 - idade }}  anos</p>
        <p>O nome tem {{ nome.length }}  caracteres</p>
        <p>O nome invertido é: {{ inverterJoao(nome.toUpperCase()) }} </p>
        <hr />
        <p> Exemplo de saudação usando função</p>
        <p> {{ saudacao() }}  </p>
    </div>
</template>


<style scoped>
.maior10{
  background-color: green;
  color: white;
}
.menor10{
  background-color: rgb(219, 101, 101);
  color: black;
}
.dez{
  background-color: rgba(128, 128, 128, 0.705);
  color: black;
}
button {
  border-radius: 6px
}

#encrementar {
  background-color: darkgreen;
  color: white;
}

#decrementar {
  background-color: rgba(255, 45, 45, 0.658);
  color: black;
}

#reset {
  background-color: rgba(128, 128, 128, 0.637);
  color: rgb(54, 51, 51);
}
.info {
  background-color: rgba(35,12,22,1);
  padding: 20px 30px;
  color: rgb(183, 210, 219);
  border-radius: 10px;
}
h1 {
  color: white;
  font-weight: bold;
  font-size: 1.5em;
}
</style>