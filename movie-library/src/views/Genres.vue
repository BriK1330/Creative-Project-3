<template>
<div>
  <div class="pure-menu pure-menu-horizontal">
    <ul class="pure-menu-list">
      <a @click="select('Action')" href="#" class="pure-menu-link"><li class="pure-menu-item">Action</li></a>
      <a @click="select('Adventure')" href="#" class="pure-menu-link"><li class="pure-menu-item">Adventure</li></a>
      <a @click="select('Animation')" href="#" class="pure-menu-link"><li class="pure-menu-item">Animation</li></a>
      <a @click="select('Comedy')" href="#" class="pure-menu-link"><li class="pure-menu-item">Comedy</li></a>
      <a @click="select('Crime')" href="#" class="pure-menu-link"><li class="pure-menu-item">Crime</li></a>
      <a @click="select('Drama')" href="#" class="pure-menu-link"><li class="pure-menu-item">Drama</li></a>
      <a @click="select('Documentary')" href="#" class="pure-menu-link"><li class="pure-menu-item">Documentary</li></a>
      <a @click="select('Fantasy')" href="#" class="pure-menu-link"><li class="pure-menu-item">Fantasy</li></a>
      <a @click="select('Horror')" href="#" class="pure-menu-link"><li class="pure-menu-item">Horror</li></a>
      <a @click="select('Mystery')" href="#" class="pure-menu-link"><li class="pure-menu-item">Mystery</li></a>
      <a @click="select('Romance')" href="#" class="pure-menu-link"><li class="pure-menu-item">Romance</li></a>
      <a @click="select('Sci-Fi')" href="#" class="pure-menu-link"><li class="pure-menu-item">Sci-Fi</li></a>
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

<style>
li {
  align-items: center;
  background-color: #FFFFFF;
  border: 1px solid rgba(0, 0, 0, 0.1);
  border-radius: .25rem;
  box-shadow: rgba(0, 0, 0, 0.02) 0 1px 3px 0;
  box-sizing: border-box;
  color: rgba(0, 0, 0, 0.85);
  cursor: pointer;
  display: inline-flex;
  font-family: system-ui,-apple-system,system-ui,"Helvetica Neue",Helvetica,Arial,sans-serif;
  font-size: 16px;
  font-weight: 600;
  justify-content: center;
  line-height: 1.25;
  margin: 0;
  min-height: 3rem;
  padding: calc(.875rem - 1px) calc(1.5rem - 1px);
  position: relative;
  text-decoration: none;
  transition: all 250ms;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
  vertical-align: baseline;
  width: auto;
}

li:hover,
li:focus {
  border-color: rgba(0, 0, 0, 0.15);
  box-shadow: rgba(0, 0, 0, 0.1) 0 4px 12px;
  color: rgba(0, 0, 0, 0.65);
}

li:hover {
  transform: translateY(-1px);
}

li:active {
  background-color: #F0F0F1;
  border-color: rgba(0, 0, 0, 0.15);
  box-shadow: rgba(0, 0, 0, 0.06) 0 2px 4px;
  color: rgba(0, 0, 0, 0.65);
  transform: translateY(0);
}
</style>
