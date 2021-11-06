<template>
<div>
  <div class="pure-menu pure-menu-horizontal">
    <ul class="pure-menu-list">
      <li class="pure-menu-item"><a @click="select('Action')" href="#" class="pure-menu-link">Action</a></li>
      <li class="pure-menu-item"><a @click="select('Adventure')" href="#" class="pure-menu-link">Adventure</a></li>
      <li class="pure-menu-item"><a @click="select('Animation')" href="#" class="pure-menu-link">Animation</a></li>
      <li class="pure-menu-item"><a @click="select('Comedy')" href="#" class="pure-menu-link">Comedy</a></li>
      <li class="pure-menu-item"><a @click="select('Crime')" href="#" class="pure-menu-link">Crime</a></li>
      <li class="pure-menu-item"><a @click="select('Drama')" href="#" class="pure-menu-link">Drama</a></li>
      <li class="pure-menu-item"><a @click="select('Documentary')" href="#" class="pure-menu-link">Documentary</a></li>
      <li class="pure-menu-item"><a @click="select('Fantasy')" href="#" class="pure-menu-link">Fantasy</a></li>
      <li class="pure-menu-item"><a @click="select('Horror')" href="#" class="pure-menu-link">Horror</a></li>
      <li class="pure-menu-item"><a @click="select('Mystery')" href="#" class="pure-menu-link">Mystery</a></li>
      <li class="pure-menu-item"><a @click="select('Romance')" href="#" class="pure-menu-link">Romance</a></li>
      <li class="pure-menu-item"><a @click="select('Sci-Fi')" href="#" class="pure-menu-link">Sci-Fi</a></li>
    </ul>
  </div>
  <MovieList :movies="movies" />
</div>
</template>

<script>
import MovieList from "../components/MovieList.vue"
export default {
  name: 'Browse',
  components: {
    MovieList
  },
  data() {
    return {
      genre: '',
    }
  },
  computed: {
    movies() {
      return this.$root.$data.movies.filter(movie => movie.genre === this.genre);
    }
  },
  methods: {
    select(genre) {
      this.genre = genre;
    }
  }
}
</script>
