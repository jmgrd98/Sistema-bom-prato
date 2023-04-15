<template>
  <div class="home">
    
    <img v-bind:src="require('../../assets/logo-restaurante.png')" id="logo"/>
    <h3>Seja bem vindo!</h3>
    <p>Escolha os ingredientes que você deseja:</p>

    <form v-on:submit.prevent="addIngredient">
    <select v-model="selected">
      <option disabled value="">Escolha um item</option>
      <option v-bind:key="ingrediente in ingredientes" v-for="ingrediente in ingredientes" value="Arroz">{{ ingrediente }}</option>
  </select>

    <button @click="addIngredient()">Adicionar</button>

    </form>

    <p>Ingredientes selecionados: {{ ingredientes }}</p>

<!--    <ul>-->
<!--      <li><router-link to="/sobre">Sobre</router-link></li>-->
<!--      <li><router-link to="/contato">Contato</router-link></li>-->
<!--    </ul>-->

  </div>
</template>

<script>

export default {
  name: 'HomePage',
  data: () => ({
    ingredientes: [
      "Arroz",
      "Feijão Carioca",
      "Feijão Preto",
      "Feijão Tropeiro",
      "Macarrão Alho e Óleo",
      "Farofa",
      "Salada (alface, tomate e repolho",
      "Legumes (beterraba, cenoura)",
      "Vinagrete"
    ],
    newArray: [],
  }),
  props: {

  },
  components: {

  },
  methods: {
    // selectIngredient: function () {
    //   for(var i = 0; i < this.ingredientes.length; i++){
    //     console.log(this.ingredientes[i]);
    //   }
    // },
    addIngredient: function () {
      this.ingredientes.push();
      console.log("Adicionou!")
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.home{
  background-color: #42b983;
  color: white;
  padding: 10px;
  border-radius: 5px;
  width: 100%;
  height: 100vh;
  margin: 0 auto;
  text-align: center;
  padding: 20px;
}

#logo{
  width: 200px;
  height: 200px;
  margin: 0 auto;
  display: block;
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
