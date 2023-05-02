<script setup>
import { ref } from 'vue'

const listaCompras = ref([
  { nome: 'Camisa Larga ', quantidade: 1 },
  { nome: 'Calça Xadrez', quantidade: 2 },
  { nome: 'Chinelo Cartago', quantidade: 3 },
  { nome: 'Bone Oakley', quantidade: 3 },
  { nome: 'Tenis Tesla', quantidade: 3 },
  { nome: 'Relogio Tommi Hilfiger', quantidade: 3 },
  { nome: 'Relogio Rolex', quantidade: 3 },
  { nome: 'Relogio Tiempo', quantidade: 3 },
  { nome: 'Perfume Pacu Rabane', quantidade: 3 },
  { nome: 'Perfume Ferrari', quantidade: 3 }
])

function incrementar(index) {
  listaCompras.value[index].quantidade++
}

</script>

<template>
  <div class="carrinho">
<button data-bs-toggle="collapse" data-bs-target="#demo">Carrinho</button>

<div id="demo" class="collapse">
  <ul>
    <li v-for="(item, index) in listaCompras">{{ item.nome }} - {{ item.quantidade }} <button @click="incrementar(index)">Incrementar</button></li>
  </ul>
</div> 
  </div>
</template>

<style scoped>
.carrinho{
  margin-top: 5%;
}
</style>
