<script>
import {Carousel, initTE} from "tw-elements";
import axios from "axios";

export default {
  data() {
    return {
      name: "Ciulek",
      movie: {
        Title: '',
        Genre: '',
        Actors: '',
        Director: '',
        Runtime: '',
        Year: '',
        Plot: '',
        Poster: '',
        Rated: '',
        Released: '',
        Language: '',

      }
    }
  },

  mounted() {

    axios.get('http://www.omdbapi.com/?apikey=ca4f67ff&i=' + this.$route.params.id)
        .then((response) => {
          // handle success
          console.log(response);
          this.movie = response.data
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
</script>

<template>
  <div class="min-h-screen flex items-center justify-center">
    <div class="bg-cinema-animation bg-cover bg-center w-screen h-screen">
      <div class="bg-transparent min-h-screen flex items-center justify-center">
        <div class="w-4/5  text-center text-gray-800 rounded-lg shadow-lg p-6">
          <div class="flex items-center justify-center">
            <img :src="movie.Poster ? movie.Poster : movie.Poster " width="300" class="w-1/3">
            <div class="text-center p-8 w-2/3">
              <h2 class="text-4xl font-bold text-blue-400 mb-4">{{ movie.Title }}</h2>
              <div class="text-xl font-bold text-blue-400 mb-4 leading-relaxed my-4 hover:scale-105 transition duration-500 cursor-pointer">Genre: <span class="text-white">{{ movie.Genre }}</span></div>
              <div class="text-xl font-bold text-blue-400 mb-4 leading-relaxed my-4 hover:scale-105 transition duration-500 cursor-pointer">Language: <span class="text-white">{{ movie.Language }}</span></div>
              <div class="text-xl font-semibold text-blue-400 mb-4 leading-relaxed my-4 hover:scale-105 transition duration-500 cursor-pointer">Age Restriction: <span class="text-white">{{ movie.Rated }}</span> </div>
              <div class="text-xl font-semibold text-blue-400 mb-4 leading-relaxed my-4 hover:scale-105 transition duration-500 cursor-pointer">Length: <span class="text-white">{{ movie.Runtime }}</span></div>
              <div class="text-xl font-semibold text-blue-400 mb-4 leading-relaxed my-4 hover:scale-105 transition duration-500 cursor-pointer">Premiere Date: <span class="text-white">{{ movie.Released}}</span></div>
              <div class="text-xl font-semibold text-blue-400 mb-4 leading-relaxed my-4 hover:scale-105 transition duration-500 cursor-pointer">Actors: <span class="text-white">{{ movie.Actors}}</span></div>
              <div class="text-2xl text-blue-400 font-semibold mb-4 leading-relaxed my-4 hover:scale-105 transition duration-500 cursor-pointer">Movie Description: <span class="text-white">{{ movie.Plot }}</span> </div>
              <a href="https://www.youtube.com" target="_blank" class="bg-blue-500 hover:bg-blue-700 text-white font-semibold py-2 px-4 rounded inline-block transition duration-300">Lookup on YT for Trailer</a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.bg-cinema-animation {
  background: linear-gradient(135deg, #2c2222, #2a0707, #281414, #3a0f0f, #111111, #0a0a0a);
  background-size: 1200% 1200%;
  animation: gradientAnimation 15s linear infinite;
}

@keyframes gradientAnimation {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}
</style>


<style>
</style>
