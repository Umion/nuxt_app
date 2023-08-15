<template>
  <div class="py-8 flex items-center justify-center">
    <button class="rounded-none bg-red-50 text-sm py-1 px-4">All</button>
    <button class="text-sm py-1 px-4">Brandibg</button>
    <button class="text-sm py-1 px-4">Design</button>
    <button class="text-sm py-1 px-4">Photo</button>
  </div>
  <div
    class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4 px-4"
  >
    <div
      v-for="item in posts"
      :key="item.id"
      class="aspect-square relative group"
    >
      <img
        class="absolute left-0 top-0 h-full w-full object-cover"
        :src="item.image"
        :alt="item.title"
      />
      <div
        class="absolute left-0 top-0 h-full w-full bg-white opacity-0 group-hover:opacity-80 transition-opacity ease-linear duration-300 flex flex-col justify-center"
      >
        <p class="text-center font-bold">{{ item.title }}</p>
        <p class="text-center text-sm">{{ item.category }}</p>
      </div>
    </div>
  </div>
  <div class="text-center pt-5">
    <NuxtLink to="/create">
      <button
        type="button"
        class="mx-auto rounded-none text-white bg-[#050708] hover:bg-[#050708]/90 font-medium rounded-lg text-sm px-10 py-3 text-center inline-flex items-center"
      >
        Create
      </button>
    </NuxtLink>
  </div>
</template>

<script setup>
useSeoMeta({
  title: "Tailwind",
  description: "This is my amazing site, let me tell you all about it.",
});

const { data: posts } = await useFetch(
  "https://my-json-server.typicode.com/Umion/fake_db/data"
);
</script>
