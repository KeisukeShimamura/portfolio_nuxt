<template>
  <header class="h-16 flex items-center z-30 w-full">
    <div class="container mx-auto px-6 flex items-center justify-between">
      <div
        class="uppercase text-gray-800 dark:text-white font-black text-3xl flex items-center"
      >
        <h1 class="text-xs ml-3 mt-1">
          <nuxt-link to="/">My Portfolio</nuxt-link>
        </h1>
      </div>
      <div class="flex items-center">
        <nav
          class="font-sen text-gray-800 dark:text-white uppercase text-lg lg:flex items-center hidden"
        >
          <a href="#" class="py-2 px-6 flex hover:text-black"> About </a>
          <a href="#" class="py-2 px-6 flex hover:text-black"> Works </a>
          <a href="#" class="py-2 px-6 flex hover:text-black"> Skill </a>
          <a href="#" class="py-2 px-6 flex hover:text-black"> Contact </a>
        </nav>
        <button class="lg:hidden flex flex-col ml-4">
          <span class="w-6 h-1 bg-gray-800 dark:bg-white mb-1"> </span>
          <span class="w-6 h-1 bg-gray-800 dark:bg-white mb-1"> </span>
          <span class="w-6 h-1 bg-gray-800 dark:bg-white mb-1"> </span>
        </button>
      </div>
    </div>
  </header>
</template>
