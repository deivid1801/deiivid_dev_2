<script setup>
const props = defineProps({
    text: String
})
</script>
<template>
    <button>{{ props.text }}</button>
    <div class="card-buttons-livros">
        <m-button @click="adicionarAoCarrinho(props.livro)" text="Adicionar ao carrinho"/>
    </div>
</template>
<style scoped>
button{
    background-color: blue;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 8px;
    color: white;
    font-size: 1.1rem;
    margin: 0 5px;
    cursor:pointer
}
button:hover{
    background-color: darkblue;
}
</style>