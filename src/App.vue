<template>
  <div id="app">
    <h3>Cadastro: </h3>
    <small id="nomeErro" v-show="deuErro">O nome é inválido, tente novamente!</small><br>
    <input type="text" placeholder="nome" v-model="nomeField"> <br>
    <input type="email" placeholder="email" v-model="emailField"> <br>
    <input type="number" placeholder="idade" v-model="idadeField"> <br>
    <button @click="cadastrarUsuario">Cadastrar</button>
    <hr>
    <!-- <h1>Guia Clientes</h1> -->
    <div v-for="(cliente,index) in clientes" :key="cliente.id">
      <h4>{{index}}</h4>
      <Cliente :cliente="cliente" @meDelete="deletarUsuario($event)"/>
      <!-- <hr>
      <h4>Edição: </h4>
      <input type="text" v-model="cliente.nome">
      <input type="text" v-model="cliente.email"> -->
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
      deuErro: false,
      nomeField: "",
      emailField: "",
      idadeField: 0,
      // nomeDoBruno: "Bruno Ap. Bandelli V.",
      // clienteBruno: {
      //   nome: "Bruno Bandelli",
      //   email: "Bruno@bandelli.com",
      //   idade: 26
      // },
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
        // {
        // id: 27,
        // nome: "Brulli",
        // email: "Brulli@bandelli.com",
        // idade: 18
        // },
        // {
        // id: 77,
        // nome: "Brunelli",
        // email: "Brunelli@bandelli.com",
        // idade: 17
        // }
      ]
    }
  },
  components: {
    Cliente,
    // Produto
  },
  methods: {
    cadastrarUsuario: function(){
      if(this.nomeField == "" || this.nomeField == " " || this.nomeField.length < 3){
        this.deuErro = true;
      }else{
      this.clientes.push({nome: this.nomeField, email: this.emailField, idade: this.idadeField, id: Date.now()});
      this.nomeField = "";
      this.emailField = "";
      this.idadeField = "0";
        this.deuErro = false;
      }
    },
      deletarUsuario: function($event){
        console.log("Recebendo evento!")
        var id = $event.idDoCliente
        var novoArray = this.clientes.filter(cliente => cliente.id != id);
        this.clientes = novoArray
        // $event.component.testar();
        // console.log($event)
        // $event.component.isPremium = true 
      }
  }
}
</script>

<style>

  #nomeErro{
    color: red
  }

</style>
