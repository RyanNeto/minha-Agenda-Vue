<template>
  <div id="painelContato">
    <div id="formularioContato">
      <form @submit="salvar">
        <label for="nome" >Nome:</label>
        <input type="text" id="nome" name="nome" v-model="nome" required>
        <label for="telefone">Celular:</label>
        <input type="text" id="telefone" name="telefone" v-model="telefone" required>
        <label for="email">E-mail:</label>
        <input type="email" id="email" name="email" v-model="email" required>

        <button>Salvar</button>
      </form>
    </div>
  </div>
</template>

<script>
import {mapActions} from "vuex";
import Contato from "../models/Contatos";

export default {
  name: "PainelContato",
  data:() =>{
    return {
      nome: "",
      telefone: "",
      email: "",
    }; 
  },
  methods:{
    ...mapActions(["salvarContato"]),
    salvar(event){
      event.preventDefault();
      const contato = new Contato(this.nome, this.telefone, this.email);
        this.salvarContato(contato);
        this.limparFormulario();
      },
      limparFormulario(){
          this.nome = "";
          this.telefone = "";
          this.email = "";
      }
  }
}
</script>

<style scoped>
#painelContato{
  font-family: "padrao1";
  font-size: 130%;
  width: 35%;
  margin: 5px auto 5px auto;
  padding: 30px;
}
#formularioContato{
  align-items: left;
  background-color: #dddddd;
  padding: 20px 40px 80px 20px;
  font-family: "padrao";
}
#nome, #email, #telefone, button{
  display: block;
  margin-bottom: 5px;
}
label{
  font-family: 'Times New Roman', Times, serif;
  
}
#nome, #telefone,#email{
    margin-top: 10px;
    height: 20px;
    padding: 8px;
    font-size: 20px;
    border-color:black;
    width: 400px;

}
input:focus{
  box-shadow: 0 0 0 0;
  outline: 0;
}
input{
  border-radius: 20px;
  outline: none;
  background-color: white;
}

button {
  background-color:#8d29bb;
  border: none;
  outline: none;
  border-radius: 8px;
  padding: 9px 4px;
  color: white;
  font-family: "padrao1";
  font-size: 120%;
  width: 160px;
  margin-top: 15px;
  float: left;
}
button:hover{
  cursor: pointer;
  background-color:purple;
  transition: 0.7s;
}
</style>