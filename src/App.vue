<script setup>
import ProductList from '@/components/ProductList.vue'
import ProductAdd from '@/components/ProductAdd.vue'
import { ref } from 'vue'


const produtos = ref([
  { id: 1, nome: 'Produto 1', preco: 'R$ 20,50' },
  { id: 1, nome: 'Produto 2', preco: 'R$ 46,50' },
  { id: 1, nome: 'Produto 3', preco: 'R$ 320,50' },
  { id: 1, nome: 'Produto 4', preco: 'R$ 25,50' }
])
 const proxId = ref(5)

function excluir(id) {
  const index = produtos.value.findIndex((produto) => produto.id === id)
  produtos.value.splice(index, 1)
}

function excluirTodos() {
  produtos.value = []
}

function adicionarProduto(produto){
  produto.id = proxId
  produtos.value.push(produtos)
  proxId.value++
}
</script>

<template>
  <h1>Meus Produtos</h1>
  <product-add @salvar="adicionarProduto"/>
  <product-list :produtos="produtos" @excluir="excluir" @apagarTudo="excluirTodos" />
</template>

<style scoped></style>
