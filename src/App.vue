<template>
  <div id="app">
    <!-- <h1>Guia Clientes</h1> -->
    <input type="text" v-model="clienteBruno.nome">
    <input type="text" v-model="clienteBruno.email">
    <Cliente :cliente="clienteBruno"/>
    <Cliente :cliente="clienteBruno"/>
    <Cliente :cliente="clienteBruno"/>
    <Cliente :cliente="clienteBruno"/>
    <!-- <hr>
      <h4>Lista de produtos!</h4>
    <hr> -->
    <!-- <Produto/>
    <Produto/>
    <Produto/> -->
  </div>
</template>

<script>
import Cliente from './components/Cliente'
// import Produto from './components/Produto'
export default {
  name: 'App',
  data(){
    return {
      nomeDoBruno: "Bruno Ap. Bandelli V.",
      clienteBruno: {
        nome: "Bruno Bandelli",
        email: "Bruno@bandelli.com",
        idade: 26
      }
    }
  },
  components: {
    Cliente,
    // Produto
  }
}
</script>

<style>

</style>
