<template>
  <h1>{{ title }}</h1>
</template>

<script>
import axios from 'axios'

export default {
  asyncData ({ params }) {
    return axios.get(`https://pokeapi.co/api/v2/pokemon-species/25`)
      .then((res) => {
        // pokemon apiを使ってみる
        // NOTE: https://pokeapi.co
        return { title: res.data.flavor_text_entries[1].flavor_text }
      })
  }
}
</script>
