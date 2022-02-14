<template>
  <h1>¿Quién es este pokémon?</h1>

  <PokemonPicture :pokemonId="4" :showPokemon="true"/>
  <PokemonOptions :pokemons="pokemonArr" />
</template>

<script>
import PokemonOptions from '@/components/PokemonOptions'
import PokemonPicture from '@/components/PokemonPicture'

import getPokemonOptions from '@/helpers/getPokemonOptions'

export default {
  components: { PokemonPicture, PokemonOptions },
  data() {
    return {
      pokemonArr: []
    }
  },
  methods: {
    async mixPokemonArr() {
      this.pokemonArr = await getPokemonOptions()
    }
  },
  mounted() {
    this.mixPokemonArr()
  }
}
</script>
