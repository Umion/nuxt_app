<template>
  <div class="min-h-screen flex flex-col">
    <Navbar />
    <div
      class="bg-[url('/assets/images/main.jpeg')] bg-no-repeat bg-fixed bg-cover bg-center flex pt-48 pb-24"
    >
      <div class="p-14 bg-white mx-auto text-center">
        <h1 class="font-medium text-2xl">We are Tailwind</h1>
        <p class="text-sm text-gray-400">Work hard. Dream big.</p>
      </div>
    </div>
    <div class="grow bg-white pt-10 pb-20 z-30 m-0 sm:mb-48">
      <div class="container mx-auto px-3">
        <slot />
      </div>
    </div>
    <Footer />
  </div>
</template>
