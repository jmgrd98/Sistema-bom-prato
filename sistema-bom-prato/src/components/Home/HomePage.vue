<template>
  <div class="home">
    
    <img v-bind:src="require('../../assets/logo-restaurante.png')" id="logo"/>
    <h3>Seja bem vindo!</h3>
    <p>Escolha os ingredientes que você deseja:</p>

    <form v-on:submit.prevent="fazerPedido">

      <div class="container">
      <input
          v-model="nome"
          type="text"
          placeholder="Digite seu nome"
          class="idInput"/>
      <input
          v-model="celular"
          type="text"
          placeholder="Informe seu celular"
          class="idInput"/>
      </div>

    <select v-model="ingrediente">
      <option disabled value="">Escolha um item</option>
      <option v-bind:key="ingrediente in ingredientes" v-for="ingrediente in ingredientes">{{ ingrediente }}</option>
  </select>

    <button @click="addIngredient">Adicionar</button>



    <p>Ingredientes selecionados: {{selectedIngredientes.toString()}}</p>

    <button type="submit" @click="fazerPedido">Fazer pedido</button>

    </form>

    <ul>
      <li></li>
      <li></li>
    </ul>

  </div>
</template>

<script>

export default {
  name: 'HomePage',
  data: () => ({
    nome: '',
    celular: '',
    ingredientes: [
      "Arroz",
      "Feijão Carioca",
      "Feijão Preto",
      "Feijão Tropeiro",
      "Macarrão Alho e Óleo",
      "Farofa",
      "Salada (alface, tomate e repolho)",
      "Legumes (beterraba, cenoura)",
      "Vinagrete"
    ],
    ingrediente: '',
    selectedIngredientes: [],
  }),
  props: {

  },
  components: {

  },
  methods: {
    selectIngredient: function () {
      console.log("Selecionou!")
    },
    addIngredient: function () {
      const selectedIngrediente = this.ingrediente;
      this.selectedIngredientes.push(selectedIngrediente);
      this.ingredientes.splice(this.ingredientes.indexOf(selectedIngrediente), 1);
      console.log(this.ingredientes)
    },
    fazerPedido: function () {
      console.log(this.nome, this.celular, this.selectedIngredientes.toString());
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.home{
  background: url(../../assets/backgroundd1.png);
  background-size: cover;
  background-repeat: no-repeat;
  color: white;
  padding: 10px;
  border-radius: 5px;
  width: 100%;
  height: 100vh;
  margin: 0 auto;
  text-align: center;
  padding: 20px;
}

@media screen and (min-width: 768px) {
  .home{
    background-size: cover;
    background-position-y: 80%;
  }
}

#logo{
  width: 200px;
  height: 200px;
  margin: 0 auto;
  display: block;
}

.container{
  margin: 10px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  gap: 5px;

  .idInput{
    width: 200px;
    height: 30px;
    border-radius: 5px;
    border: none;
    padding: 5px;
  }
}

select{
  width: 200px;
  height: 30px;
  border-radius: 5px;
  border: none;
  padding: 5px;
  margin: 10px;
}

button{
  width: 200px;
  height: 30px;
  border-radius: 5px;
  border: none;
  padding: 5px;
  margin: 10px;
  background-color: #42b983;
  color: white;
  cursor: pointer;
  transition: width, height;
  transition-duration: .5s;
}

button:hover{
  width: 210px;
  height: 35px;
  border-radius: 5px;
  border: none;
  padding: 5px;
  margin: 10px;
  background-color: #42b983;
  border: 1px solid white;
  color: white;
  cursor: pointer;
}

h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
