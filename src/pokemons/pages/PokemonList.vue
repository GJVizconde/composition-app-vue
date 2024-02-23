<script setup lang="ts">


import PokemonCardList from '../components/PokemonCardList.vue';
import { usePokemon } from '../composables/usePokemons';

const {count, pokemons, isLoading, isError, error} = usePokemon()


// const { isLoading, data:pokemons, } = useQuery({
//     queryKey: ['pokemons'],
//     queryFn: getPokemons,
// })


// const count = computed(()=> pokemons.value?.length ?? 0)



</script>
<template>

    <h1 v-if="isLoading">Loading...</h1>

    <div v-else-if="isError">
        {{ error }}

    </div>


    <div v-else>
        <h1>Pokemon List - ({{ count }})</h1>

        <PokemonCardList
            :pokemons ="pokemons ?? []"
        />


    </div>
</template>
