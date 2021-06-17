<template>
  <div id="app">
    <!-- <h1>Guia Clientes</h1> -->
    <div v-for="(cliente,index) in clientes" :key="cliente.id">
      <h4>{{index}}</h4>
      <Cliente :cliente="cliente"/>
      <hr>
      <h4>Edição: </h4>
      <input type="text" v-model="cliente.nome">
      <input type="text" v-model="cliente.email">
    </div>
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
      },
      clientes: [
        {
        id: 7,
        nome: "Bruno",
        email: "Bruno@bandelli.com",
        idade: 26
        },
        {
        id: 14,
        nome: "Bandelli",
        email: "Bandelli@bandelli.com",
        idade: 21
        },
        {
        id: 27,
        nome: "Brulli",
        email: "Brulli@bandelli.com",
        idade: 18
        },
        {
        id: 77,
        nome: "Brunelli",
        email: "Brunelli@bandelli.com",
        idade: 17
        }
      ]
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
