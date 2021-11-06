<template>
<div class="wrapper">
  <div class="movies">
    <div class="movie" v-for="movie in movies" :key="movie.id">
      <div class="info">
        <h1>{{movie.title}}</h1>
        <p><em>{{movie.genre}}</em></p>
        <p>Duration: {{movie.duration}} mins</p>
      </div>
      <!-- <div class="image">
        <img :src="'/images/movies/'+movie.image">
      </div> -->
      <div class="duration">
        <p><em>Producer: {{movie.producer}}</em></p>
        <!-- <button v-on:click="addToCart(movie)" class="auto">Add to Cart</button> -->
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
  // methods: {
  // }
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

.movie img {
  border: 2px solid #333;
  height: 250px;
  width: 200px;
  object-fit: cover;
}

.movie .image {
  display: flex;
  justify-content: center;
  margin-bottom: 5px;
}

.info {
  background: #799fad;
  color: #000;
  padding: 10px 30px;
  height: 150px;
}

.info h1 {
  font-size: 14px;
}

.info p {
  text-align: center;
  margin: 0px;
  font-size: 12px;
}


.duration {
  display: flex;
}

.auto {
  margin-left: auto;
}
</style>
