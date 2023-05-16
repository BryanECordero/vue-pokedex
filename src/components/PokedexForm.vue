<template>
    <form class="pokemon-form" method="dialog">
        <input
        class="pokemon-input"
        type="text"
        name="pokemon"
        v-model="pokemonName"
        placeholder="Busca tu pokemon"
        autocomplete="off"/>
        <input type="button" @click="sendId" value="&#xe8b6;" class="pokemon-btn material-icons">
    </form>
</template>

<script>
    
export default {
    name: 'PokedexForm',

    data () {
        return {
        pokemonName: ''
        }
    },
    emits: ['response'],
    methods: {
        sendId () {
            const newPokemonId = window.isNaN(parseInt(this.pokemonName)) ? this.pokemonName.toLowerCase() : this.pokemonName
            this.$emit('response', newPokemonId)
        }
    }
}
</script>
