<template>
  <div>
      <div class="mt-4" v-for="(genre, index) in genres" :key="index">
          <div class="container">
             <div class="row">
                <div class="container" v-for="(movie, index) in movies[genre]['movies']" :key="index">
                  <div v-if="proId == movie.Id">
                  <iframe class="shadow p-3 mb-5 bg-white rounded" width="560" height="315" :src="movie.videoUrl" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                 </div>
              </div>
                <div class="mt-2" v-for="(movie, index) in movies[genre]['movies']" :key="index">
                  <div v-if="proId == movie.Id">
                    <h2>{{movie.title}}</h2>
                    <p>{{movie.description}}</p>
                    <p>{{movie.year}}</p>
                 </div>
              </div>
            </div>
          </div>
      </div>
  </div>
</template>

<script>
import movieData from '@/data/MoviesData.json'

export default {
  name: 'details',
  data () {
    return {
      proId: this.$route.params.Pid,
      movies: movieData,
      genres: []
    }
  },
  mounted () {
    this.genres = Object.keys(this.movies)
  }
}
</script>

<style>
@media screen and (max-width:576px) {
  iframe {
    width:100%;
  }
}

@media screen and (min-width:576px) {
  iframe {
    width:540px;
  }
}

@media screen and (min-width:768px) {
  iframe {
    width:720px;
  }
}

@media screen and (min-width:992px) {
  iframe {
    width:960px;
  }
}

@media screen and (min-width:1200px) {
  iframe {
    width:1140px;
  }
}

</style>
