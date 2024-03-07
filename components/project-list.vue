<template>
    <p class="mb-10">Take a  look at pokemon list</p>
    <section v-if="pending">Loading ....</section>
    <section v-else-if="error">Something wnet wrong ... Try again.</section>
    <section v-else>
        <ul class="grid grid-cols-1 gap-4">
            <li v-for="poke in data.results" :key="poke.id" 
            class="border border-gray-200 rounded-sm p-4 hover:bg-gray-100 font-mono">
            
            <a :href="poke.url">
                <div class="font-semiblod"> {{ poke.name }}</div>
            </a>
            </li>
        </ul>
    </section>
</template>

<script setup>
const { error, pending, data } = await useFetch('https://pokeapi.co/api/v2/pokemon/')
console.log(data)
</script>