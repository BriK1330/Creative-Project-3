<template>
<div class="wrapper">
  <div class="movies">
    <div class="movie" v-for="movie in movies" :key="movie.id">
      <div class="info">
        <h1>{{movie.title}}</h1>
        <p><em>{{movie.genre}}</em><br>Duration: <u>{{movie.duration}} mins</u></p>
      </div>
      <div class="duration">
        <p>Producer: <em>{{movie.producer}}</em></p>
        <button v-on:click="switchToMovie(movie.id)" class="auto">More Info</button>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'MovieList',
  props: {
    movies: Array
  },
  methods: {
    switchToMovie(id) {
      this.$router.push(`/movie/${id}`);
    }
  }
}
</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.movies {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.movie {
  margin: 10px;
  margin-top: 50px;
  width: 200px;
}

.info {
  background: #799fad;
  color: #000;
  padding: 10px 30px;
  height: 125px;
}

.info h1 {
  font-size: 14px;
  text-align: center;
}

.info p {
  text-align: center;
  margin: 0px;
  font-size: 14px;
  margin-bottom: 8px;
}

.duration {
  display: flex;
}

.auto {
  margin-left: auto;
}

button {
  text-align: center;
  background-color: #464b4d;
  color: #ccbe1f;
  height: 35px;
}
</style>
