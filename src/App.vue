<script setup>
import { ref } from 'vue'
const contador = ref(0)
function icrementarContador() {
  contador.value++
}
function decrementarContador() {
  if (contador.value > 0) {
    contador.value--
  }
}
function resetContador() {
  contador.value = 0
}

</script>

<template>
<button id="icrementar" @click="icrementarContador">+</button>
<button id="decrementar" @click="decrementarContador">-</button>
<button id="reset" @click="resetContador">Resetar</button>
<br>
<p>Valor do contador é = {{ contador }}</p>
</template>
<style scoped>
button {
  border-radius: 6px
}

#icrementar {
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
</style>