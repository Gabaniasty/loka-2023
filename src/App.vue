<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <header>
      <div class="bg-black px-40 sticky top-0 z-10">
        <ul class="flex flex-row items-center justify-around font-semibold py-6 rounded-lg dark:bg-gray-800 dark:border-gray-700">

          <RouterLink class="flex items-center" to="/home">
            <img src="https://flowbite.com/docs/images/logo.svg" class="h-8" alt="Extra Bio" />
            <span class="self-center text-2xl ml-4 font-semibold whitespace-nowrap text-white">Sambíó</span>
          </RouterLink>


          <li>
            <RouterLink class="block py-2 pl-3 pr-4 text-white bg-blue-700 rounded md:bg-transparent md:text-blue-700 md:p-0" to="/about" aria-current="page"></RouterLink>
          </li>

          <li>
            <RouterLink class="block py-2 pl-3 pr-4 text-gray-300 rounded hover:bg-blue-400 md:hover:bg-transparent md:border-0 md:hover:text-blue-400 md:p-0 hover:scale-125 transition duration-500 cursor-pointer" to="/home">WHAT'S ON</RouterLink>
          </li>

          <li>
            <RouterLink class="block py-2 pl-3 pr-4 text-gray-300 rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-blue-400 md:p-0 hover:scale-125 transition duration-500 cursor-pointer" to="/movies">ABOUT US</RouterLink>
          </li>
        </ul>
      </div>

    <RouterView />



  </header>


</template>

