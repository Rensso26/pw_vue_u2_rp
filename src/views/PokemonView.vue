<template>
 
 <Pokemonimagen :pokemonId="1"/>
 <Pokemonopciones/>
</template>

<script>
import Pokemonimagen from '@/components/pokemonimagen.vue';
import Pokemonopciones from '@/components/pokemonopciones.vue';

export default {
    components: {
        Pokemonimagen,
        Pokemonopciones
    }
}
</script>

<style>

</style>