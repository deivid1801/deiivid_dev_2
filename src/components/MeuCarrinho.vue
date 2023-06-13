<script>
import MButton from './MButton.vue';
</script>
<template> <div v-if="botao">
    <ul>
        <li v-for="car in carrinho" :key="car.id">{{ car.nome }} - Qtd:{{ car.quantidade }}
            <button class="btn btn-info" @click="adicionar(car.id)">+</button>
            <button class="btn btn-info" @click="diminuir(car.id)">-</button>
            <p>Total a pagar:R$ {{ car.preco * car.quantidade }}</p>
            <m-button />

        </li>
    </ul>
</div></template>
<style>
    
</style>