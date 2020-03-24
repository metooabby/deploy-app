<template>
  <div class="home">
      <div class="mt-4" v-for="(genre, index) in genres" :key="index">
          <div class="container-md">
              <h4>{{genre}}</h4>
             <div class="row">
               <div class="shadow-lg p-1 mb-5 bg-white rounded" v-for="(movie, index) in movies[genre]['movies']" :key="index">
                  <div @click="goTodetail (movie.Id)">
                    <img :src="movie.thumbUrl" class="img-fluid" />
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
  name: 'Home',
  data () {
    return {
      movies: movieData,
      genres: []
    }
  },
  mounted () {
    this.genres = Object.keys(this.movies)
  },
  methods: {
    goTodetail (proId) {
      this.$router.push({ name: 'details', params: { Pid: proId } })
    }
  }
}
</script>

<style lang='scss' scoped>
img {
  border-radius: 5px;
  max-width: 100%;
  margin-bottom: 10px;
}

h4 {
  font-weight: 900;
  color: #ffffff;
}
</style>
