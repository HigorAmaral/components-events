<script setup>
import {reactive} from 'vue'
const emit = defineEmits(['Adicionar'])
const produto = reactive({
    nome: '',
    preco: ''
})

function salvar() {
    if(produto.nome === ''){
        alert("O produto não poder ser vazio")
        return
    }
    emit()
}
</script>

<template>
    <form @submit.prevent="salvar">
        <div>
            <label for="nome">Nome</label>
            <input type="text" id="nome" v-model="produto.nome">
        </div>
        <div>
            <label for="preço">Preço</label>
            <input type="text" id="preço" v-model="produto.preco">
        </div>
        <button type="submit" @click="salvar">Salvar</button>
    </form>
</template>

<style scoped>
</style>