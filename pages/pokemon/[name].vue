<template>
  <div class="container mx-auto px-4 py-12">
    
    <div class="grid md:grid-cols-2 gap-8">

      <div class="space-y-4">
        <div class="bg-gray-100 rounded-lg overflow-hidden relative">
          <img :src="data.sprites.front_default" class="w-full h-full object-cover object-center" />
        </div>
      </div>

      <div class="md:py-8">
        <div class="mb-2 md:mb-3">
          <span class="inline-block text-gray-500 mb-1">
            #{{ data.id}}
          </span>
          <h1 class="text-gray-800 text-2xl lg:text-3xl font-bold">
            {{ data.name }}
          </h1>

        </div>
      </div>
    </div>

    <hr class="my-8"/>

    <NuxtLink class="button" to="/">
      Back
    </NuxtLink>
    
  </div>
</template>

<script setup>
const route = useRoute()
const name = route.params.name

const { data } = await useFetch(`https://pokeapi.co/api/v2/pokemon/${name}`)
</script>