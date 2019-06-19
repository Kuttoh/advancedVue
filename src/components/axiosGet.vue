<template>
  <div class="hello">
    <em><p>Description Data:</p></em>
    Object: <b>{{pokemon.descriptions[0]}}</b>
    <br>

    <em><p>Breaking it down:</p></em>
    Description: <b>{{ pokemon.descriptions[0].description}}</b>
    <br>
    Language Name: <b>{{ pokemon.descriptions[0].language.name}}</b>
    <br>
    The URL is: <b>{{ pokemon.descriptions[0].language.url}}</b>

    <em><p>Other responses:</p></em>
    {{otherResponses}}

  </div>
</template>

<script>
  import axios from 'axios'
export default {
  name: 'HelloWorld',

  data () {
    return {
      pokemon : {},
      otherResponses: {}

    }
  },

  created () {
    axios.get('https://pokeapi.co/api/v2/pokedex/kanto/')
            .then(response => {
              console.log(response)
              this.pokemon = response.data,
              this.otherResponses= [response.status, response.statusText, response.headers, response.config]
            })
            .catch(err => {
              console.log(err)
            })
  }


}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
