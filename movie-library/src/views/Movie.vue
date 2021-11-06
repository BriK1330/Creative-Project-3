<template>
<div>
  <div class="info">
    <h1>{{movie.title}}</h1>
    <h3>Producer: <em>{{movie.producer}}</em> <br>Duration: <em>{{movie.duration}}</em><br>
    Genre: <em>{{movie.genre}}</em></h3>
    <p><strong>Description:</strong> {{movie.description}}</p>
  </div>
</div>
</template>

<script>
export default {
  name: 'Home',
  data() {
    return {
      movie: {},
    }
  },
  created() {
    this.movie = this.$root.$data.movies.find(movie => movie.id === parseInt(this.$route.params.id));
  },
}
</script>

<style scoped>
.intro {
  font-style: italic;
}

.movies {
  display: flex;
  flex-wrap: wrap;
}

.info h1 {
  text-align: center;
}

.info h3 {
  text-align: center;
}

.info p {
  align-content: center;
  text-align: center;
}
</style>
