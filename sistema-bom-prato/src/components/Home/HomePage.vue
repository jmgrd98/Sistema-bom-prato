<template>
  <div class="home">
    
    <img v-bind:src="require('../../assets/logo-restaurante.png')" id="logo"/>
    <h3>Seja bem vindo!</h3>
    <p>Escolha os ingredientes que você deseja:</p>

    <form v-on:submit.prevent="addIngredient">
    <select v-model="selected">
      <option disabled value="">Escolha um item</option>
      <option value="Arroz">Arroz</option>
      <option value="Feijão Carioca">Feijão Carioca</option>
      <option value="Feijão Preto">Feijão Preto</option>
      <option value="Feijão Tropeiro">Feijão Tropeiro</option>
      <option value="Macarrão Alho e Óleo">Macarrão Alho e Óleo</option>
      <option value="Farofa">Farofa</option>
      <option value="Salada (alface, tomate e repolho">Salada (alface, tomate e repolho)</option>
      <option value="Legumes (beterraba, cenoura)">Legumes (beterraba, cenoura)</option>
      <option value="Vinagrete">Vinagrete</option>
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
    ingredientes: [],
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
      this.selected.push(this.selected);
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
