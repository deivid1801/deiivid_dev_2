<script setup>
import { ref } from 'vue'

const listaCompras = ref([
  { nome: 'São Paulo', quantidade: 1 },
  { nome: 'Rio de Janeiro', quantidade: 2 },
  { nome: 'Belo Horizonte', quantidade: 3 },
  { nome: 'Salvador', quantidade: 3 },
  { nome: 'Fortaleza', quantidade: 3 },
  { nome: 'Curitiba', quantidade: 3 },
  { nome: 'Manaus', quantidade: 3 },
  { nome: 'Recife', quantidade: 3 },
  { nome: 'Porto Alegre', quantidade: 3 },
  { nome: 'Brasília', quantidade: 3 }
])

function incrementar(index) {
  listaCompras.value[index].quantidade++
}

</script>

<template>
  <ul>
    <li v-for="(item, index) in listaCompras">{{ item.nome }} - {{ item.quantidade }} <button @click="incrementar(index)">Incrementar</button></li>
  </ul>
</template>

<style scoped>

</style>
