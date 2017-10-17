<template>
  <div id="app">
    <div class="container">
      <h3>Data completa</h3>
      <div v-for="(el, idx) in news" :key="idx">
        {{el.item}}
      </div>
      <div class="separator"></div>
      <h3>Data recortada</h3>
      <div v-for="(el, idx) in news" :key="idx">
        {{el.item | subString(20)}}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      news: [
        { 'item': 'Pokémon Rojo y Pokémon Azul' },
        { 'item': 'Pokémon Amarillo' },
        { 'item': 'Pokémon Oro y Pokémon Plata' },
        { 'item': 'Pokémon Rubí y Pokémon Zafiro' },
        { 'item': 'Pokémon Diamante y Pokémon Perla' },
        { 'item': 'Pokémon Negro y Pokémon Blanco' },
        { 'item': 'Pokémon X y Pokémon Y' },
        { 'item': 'Pokémon Sol y Pokémon Luna' }
      ]
    }
  },
  filters: {
    subString: function (el, value) {
      // console.log('Este es el elemento: ' + el)
      // console.log('Este es el valor numero de caracteres: ' + value)
      if (el.length >= value) {
        //retornamos el contenido recortado, ademas de agregar 3 puntos.
        return el.substring(0, value) + '...'
      } else {
        //retornamos el texto sin cambios.
        return el
      }
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
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
