

<style>

.selected {
  visibility: visible;
}

@keyframes sparkle {
  0% {
    opacity: 0;
    transform: scale(0.5);
  }
  50% {
    opacity: 1;
    transform: scale(1);
  }
  100% {
    opacity: 0;
    transform: scale(0.5);
  }
}

.animate-sparkle {
  animation: sparkle 1s infinite;
}
</style>



<script>
import axios from 'axios';
import TheWelcome from '../components/TheWelcome.vue'
import { onMounted } from 'vue'
// Initialization for ES Users
import {
  Carousel,
  initTE,
} from "tw-elements";

export default {
  data() {
    return {
      name: "",
      movies:[]
    }
  },

  computed: {
    upperCaseName() {
      return this.name.toUpperCase();
    },

    filteredMovies() {
      if (this.$route.query.cinema) {
        return this.movies.filter((movie) => movie['showtimes'].hasOwnProperty(this.$route.query.cinema));
      }
      return this.movies;
    }
  },

  mounted() {
    initTE({ Carousel });

    axios.get('https://grouplimit.co/api/v1/cinema/LFZHAia7t0NjjJ62F2pB')
        .then((response) => {
          // handle success
          console.log(response);
          this.movies = response.data.data
        })
        .catch(function (error) {
          // handle error
          console.log(error);
        })
        .finally(function () {
          // always executed
        });
  }
}

function toggleSelection(id) {
  const checkbox = document.getElementById(id);
  const checkmark = document.getElementById(`checkmark_${id}`);
  checkbox.checked = !checkbox.checked;
  checkmark.classList.toggle('hidden', !checkbox.checked);
}

</script>

<template>
    <div class="relative" id="carouselExampleCaptions" data-te-carousel-init data-te-ride="carousel">
      <div
          class="absolute bottom-0 left-0 right-0 z-[2] mx-[15%] mb-4 flex list-none justify-center p-0"
          data-te-carousel-indicators>
        <button
            type="button"
            data-te-target="#carouselExampleCaptions"
            data-te-slide-to="0"
            data-te-carousel-active
            class="mx-[3px] box-content h-[3px] w-[30px] flex-initial cursor-pointer border-0 border-y-[10px] border-solid border-transparent bg-white bg-clip-padding p-0 -indent-[999px] opacity-50 transition-opacity duration-[600ms] ease-[cubic-bezier(0.25,0.1,0.25,1.0)] motion-reduce:transition-none"
            aria-current="true"
            aria-label="Slide 1"></button>
        <button
            type="button"
            data-te-target="#carouselExampleCaptions"
            data-te-slide-to="1"
            class="mx-[3px] box-content h-[3px] w-[30px] flex-initial cursor-pointer border-0 border-y-[10px] border-solid border-transparent bg-white bg-clip-padding p-0 -indent-[999px] opacity-50 transition-opacity duration-[600ms] ease-[cubic-bezier(0.25,0.1,0.25,1.0)] motion-reduce:transition-none"
            aria-label="Slide 2"></button>
        <button
            type="button"
            data-te-target="#carouselExampleCaptions"
            data-te-slide-to="2"
            class="mx-[3px] box-content h-[3px] w-[30px] flex-initial cursor-pointer border-0 border-y-[10px] border-solid border-transparent bg-white bg-clip-padding p-0 -indent-[999px] opacity-50 transition-opacity duration-[600ms] ease-[cubic-bezier(0.25,0.1,0.25,1.0)] motion-reduce:transition-none"
            aria-label="Slide 3"></button>
      </div>

      <!--Carousel items-->
      <div
          class="relative w-full overflow-hidden after:clear-both after:block after:content-['']">
        <!--First item-->
        <div
            class="relative inline float-left -mr-[100%] w-full transition-transform duration-[600ms] ease-in-out motion-reduce:transition-none"
            data-te-carousel-active
            data-te-carousel-item
            style="backface-visibility: hidden">
          <img
              src="https://m.media-amazon.com/images/S/pv-target-images/1b6f5eb81ea07b0ced94d8202e038e60a5b35b08f26c17d848dc2914134801c9.jpg"
              class="block w-full"
              alt="Out" />
          <div
              class="absolute inset-x-[15%] bottom-5 hidden py-5 text-center text-white md:block">
            <h5 class="text-xl">SAW X</h5>
          </div>
        </div>
        <!--Second item-->
        <div
            class="relative inline  float-left -mr-[100%] hidden w-full transition-transform duration-[600ms] ease-in-out motion-reduce:transition-none"
            data-te-carousel-item
            style="backface-visibility: hidden">
          <img
              src="https://variety.com/wp-content/uploads/2023/08/MCDEXBE_UV001.jpg"
              class="block w-full"
              alt="Upcoming Cinema " />
          <div
              class="absolute inset-x-[15%] bottom-5 hidden py-5 text-center text-white md:block">
            <h5 class="text-xl">The Exorcist: Believer</h5>
          </div>
        </div>
        <!--Third item-->
        <div
            class="relative inline float-left -mr-[100%] hidden w-full transition-transform duration-[600ms] ease-in-out motion-reduce:transition-none"
            data-te-carousel-item
            style="backface-visibility: hidden">
          <img
              src="https://nofilmschool.com/media-library/the-creator-review.jpg?id=45875716&width=1245&height=700&quality=90&coordinates=0%2C0%2C0%2C0"
              class="block w-full"
              alt="..." />
          <div
              class="absolute inset-x-[15%] bottom-5 hidden py-5 text-center text-white md:block">
            <h5 class="text-xl">The Creator</h5>
          </div>
        </div>
      </div>

      <!--Carousel controls - prev item-->
      <button
          class="absolute bottom-0 left-0 top-0 z-[1] flex w-[15%] items-center justify-center border-0 bg-none p-0 text-center text-white opacity-50 transition-opacity duration-150 ease-[cubic-bezier(0.25,0.1,0.25,1.0)] hover:text-white hover:no-underline hover:opacity-90 hover:outline-none focus:text-white focus:no-underline focus:opacity-90 focus:outline-none motion-reduce:transition-none"
          type="button"
          data-te-target="#carouselExampleCaptions"
          data-te-slide="prev">
    <span class="inline-block h-8 w-8">
      <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="currentColor"
          class="h-6 w-6">
        <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M15.75 19.5L8.25 12l7.5-7.5" />
      </svg>
    </span>
        <span
            class="!absolute !-m-px !h-px !w-px !overflow-hidden !whitespace-nowrap !border-0 !p-0 ![clip:rect(0,0,0,0)]"
        >Previous</span
        >
      </button>
      <!--Carousel controls - next item-->
      <button
          class="absolute bottom-0 right-0 top-0 z-[1] flex w-[15%] items-center justify-center border-0 bg-none p-0 text-center text-white opacity-50 transition-opacity duration-150 ease-[cubic-bezier(0.25,0.1,0.25,1.0)] hover:text-white hover:no-underline hover:opacity-90 hover:outline-none focus:text-white focus:no-underline focus:opacity-90 focus:outline-none motion-reduce:transition-none"
          type="button"
          data-te-target="#carouselExampleCaptions"
          data-te-slide="next">
    <span class="inline-block h-8 w-8">
      <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="currentColor"
          class="h-6 w-6">
        <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M8.25 4.5l7.5 7.5-7.5 7.5" />
      </svg>
    </span>
        <span
            class="!absolute !-m-px !h-px !w-px !overflow-hidden !whitespace-nowrap !border-0 !p-0 ![clip:rect(0,0,0,0)]"
        >Next</span
        >
      </button>
    </div>

  <div class="flex items-center justify-center mt-3">
    <div class="bg-white shadow-lg rounded-lg p-6">
      <h2 class="text-2xl font-bold mb-6 text-center">Choose a Cinema</h2>
      <div class="flex space-x-4">
      <router-link class="hover:scale-110 hover:text-blue-500" :to="{ path: '/home', query: {cinema: 'Laugarásbíó'} }">Laugarásbíó</router-link>
      <router-link class="hover:scale-110 hover:text-blue-500" :to="{ path: '/home', query: {cinema: 'Sambíóin Egilshöll'} }">Sambíóin Egilshöll</router-link>
      <router-link class="hover:scale-110 hover:text-blue-500" :to="{ path: '/home', query: {cinema: 'Sambíóin Kringlunni'} }">Sambíóin Kringlunni</router-link>
      <router-link class="hover:scale-110 hover:text-blue-500" :to="{ path: '/home', query: {cinema: 'Sambíóin Álfabakka'} }">Sambíóinn Álfabakka</router-link>
      <router-link class="hover:scale-110 hover:text-blue-500" :to="{ path: '/home', query: {cinema: 'Smárabíó'} }">Smárabíó</router-link>
      <router-link class="hover:scale-110 hover:text-blue-500" :to="{ path: '/home', query: {cinema: 'Bíó Paradís'} }">Bíó Paradís</router-link>
      </div>
    </div>
  </div>


    <div class="mainaligner flex justify-center flex-wrap ml-6 mr-6 mt-12 sparkles-container relative">
      <div class="w-1/5 pr-2 pl-2" v-for="movie in filteredMovies">
        <div class="bg-blue mb-2 p-3 rounded-lg my-4 hover:scale-90 transition duration-500 cursor-pointer ">
          <h3 class="text-white text-2xl mb-4 overflow-hidden flex justify-center">
            <span class="truncate">{{ movie["name"] }}</span>
          </h3>
          <div class="flex justify-center">
            <router-link :to="'/about/' + movie.imdbID">
              <img :src="movie.poster ? movie.poster : '/notf.jpg'" width="300">
            </router-link>
          </div>
          <div class="rating ml-4">
              <p v-if="movie['imdb_rating'] == 0 " class="text-white">
                Rating: <span class="text-red-400"> Rating is not available! </span>
              </p>
              <p v-else-if="movie['imdb_rating'] >= 5 " class="text-white mt-2">
                Rating: <span class="text-green-300"> {{ movie.imdb_rating }} </span>
              </p>

              <p v-else-if="movie['imdb_rating'] < 5 " class="text-white">
                Rating: <span class="text-red-500"> {{ movie.imdb_rating }} </span>
              </p>



              <p class="text-white">Year: {{ movie["year"] }} </p>
              <p v-for="(show,name) in movie['showtimes']" class="text-white mt-3">
                <div v-if="!$route.query.cinema || $route.query.cinema == name">
                  {{ name }}
                  <p v-for="stime in show" class="text-blue-400">{{ stime.time.replace(".", ":") }} {{ stime.location }}</p>
                </div>
              </p>
          </div>
        </div>
      </div>
    </div>

  <footer class="bg-gray-800 text-white p-4 text-center">
    <div class="container mx-auto">
      <p>&copy; 2023 Sambíó. All rights reserved.</p>
    </div>
  </footer>
</template>
