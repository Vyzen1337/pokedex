<template>
  <div class="container mx-auto px-4">

    <h1 class="text-gray-800 text-2xl lg:text-3xl font-bold my-12">
      Pokédex
    </h1>

    <!-- <pre>{{ data }}</pre> -->
    

    <!-- <pre>
      {{ data }}
    </pre> -->

    <div class="grid sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-x-4 md:gap-x-6 gap-y-6">

      <div v-for="(item) in data.results">

        <div class="flex flex-col">
          <span class="text-gray-500">
            {{ item.name }}
          </span>
          <NuxtLink :to="`/pokemon/${item.name}`">
            read more
          </NuxtLink>

          
        </div>
      </div>

    </div>



  </div>
</template>

<script setup>
const { data } = await useFetch('https://pokeapi.co/api/v2/pokemon/')

</script>