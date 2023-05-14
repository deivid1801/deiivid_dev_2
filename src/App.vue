<script setup>
import { ref } from 'vue'
const produtos = ref([
    {
        id: 1,
        nome: 'Camiseta',
        preco: 49.90,
        quantidade: 1
    },
    {
        id: 2,
        nome: 'Calça',
        preco: 99.90,
        quantidade: 1
    },
    {
        id: 3,
        nome: 'Meia',
        preco: 9.90,
        quantidade: 1
    },
    {
        id: 4,
        nome: 'Sapato',
        preco: 199.90,
        quantidade: 1
    },
    {
        id: 5,
        nome: 'Boné',
        preco: 29.90,
        quantidade: 1
    },
    {
        id: 6,
        nome: 'Óculos',
        preco: 99.90,
        quantidade: 1
    },
    {
        id: 7,
        nome: 'Relógio',
        preco: 299.90,
        quantidade: 1
    },
    {
        id: 8,
        nome: 'Bermuda',
        preco: 79.90,
        quantidade: 1
    },
    {
        id: 9,
        nome: 'Cueca',
        preco: 19.90,
        quantidade: 1
    },
    {
        id: 10,
        nome: 'Meia',
        preco: 9.90,
        quantidade: 1
    }
])

const carrinho = ref([])

const botao = ref(false)


function bot() {
    botao.value = !botao.value; 
}

function adicionar(id) {
    const index = carrinho.value.findIndex(item => item.id === id)
    carrinho.value[index].quantidade++
}

function diminuir(id) {
  const index = carrinho.value.findIndex(item => item.id === id)
if(carrinho.value[index].quantidade > 0){
    carrinho.value[index].quantidade--
}
}



function addToCart(id, nome, preco, quantidade) {
    carrinho.value.push({id, nome, preco, quantidade});
}
function retirar(index){
    carrinho.value.splice(index, 1)
}
</script>

<template>
    <div class="container-fluid">
    </div>
    <div>
        <ul>
            <li v-for="item in produtos" :key="item.id">{{ item.nome }} - {{ item.preco.toLocaleString('pt-br',{style: 'currency', currency: 'BRL'}) }}
                <button @click="addToCart(item.id, item.nome, item.preco, item.quantidade)" class="btn btn-outline-primary">adicionar ao carrinho</button>
                <button @click="retirar(index)" class="btn btn-outline-primary">retirar do carrinho</button>
            </li>
        </ul>
    </div>
    <button @click="bot" type="button" class="btn btn-primary">Mostrar carrinho</button>

    <div v-if="botao">
        <ul>
            <li v-for="car in carrinho" :key="car.id">{{ car.nome }} - Qtd:{{ car.quantidade }}
                <button class="btn btn-info" @click="adicionar(car.id)">+</button>
                <button class="btn btn-info" @click="diminuir(car.id)">-</button>
                <p>Total a pagar:R$ {{ car.preco * car.quantidade }}</p>
            </li>
        </ul>
    </div>
</template>

<style scoped>
</style>
