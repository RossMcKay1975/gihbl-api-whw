<template>
  <div>
    <h1>The World of Ghibli</h1>
    <div class="main-container">
      <films-list :films="films"></films-list>
      <film-detail :film="selectedFilm"></film-detail>
    </div>
  </div>
</template>

<script>
import { eventBus } from './main.js'
import FilmsList from './components/FilmsList.vue';
import FilmDetail from './components/FilmDetail.vue'

export default {
  name: 'app',
  data(){
    return {
      films: [],
      selectedFilm: null
      }
    },
    components: {
      "films-list": FilmsList,
      "film-detail": FilmDetail
    },
  mounted(){
    fetch('https://ghibliapi.herokuapp.com/films')
    .then(res => res.json())
    .then(films => this.films = films)

    eventBus.$on('film-selected', (film) => {
      this.selectedFilm = film
    })
  }
}

</script>

<style lang="css" scoped>
h1 {
  text-align: center;
  color: #333;
}
.main-container {
  display: flex;
  justify-content: space-between;
  width: 80%;
  margin: 0 auto;
}
</style>
