<template>
  <div class="home">
    
    <img v-bind:src="require('../../assets/logo-restaurante.png')" id="logo"/>
    <h3>Seja bem vindo!</h3>
    <p>Escolha os ingredientes que você deseja:</p>
    <select v-model="selected">
      <option disabled value="">Escolha um item</option>
      <option>Arroz</option>
      <option>Feijão Carioca</option>
      <option>Feijão Preto</option>
      <option>Feijão Tropeiro</option>
      <option>Macarrão Alho e Óleo</option>
      <option>Farofa</option>
      <option>Salada (alface, tomate e repolho)</option>
      <option>Legumes (beterraba, cenoura)</option>
      <option>Vinagrete</option>
  </select>

    <p>Ingredientes selecionados: {{ selected }}</p>

<!--    <ul>-->
<!--      <li><router-link to="/sobre">Sobre</router-link></li>-->
<!--      <li><router-link to="/contato">Contato</router-link></li>-->
<!--    </ul>-->

  </div>
</template>

<script>

export default {
  name: 'HomePage',
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
  props: {

  },
  components: {

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
