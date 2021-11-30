<template>
  <div id="app">
    <!-- header -->
    <header>
      <MySelect :genres ="genresList" @cheangedGenre ="startSearch"/>
    </header>

    <!-- main -->
    <main>
      <!-- componenti main -->
      <MyListmusic :selectedGenre ="genreToSearch" @genresReady ="getGenresList"/>
    </main>
  </div>
</template>

<script>
import MySelect from './components/MySelect.vue';
import MyListmusic from './components/MyListmusic.vue';

export default {
  name: 'App',
  components: {
    MySelect,
    MyListmusic
  },
  data() {
    return {
      genresList: [],
      genreToSearch: "",
    }
  },
  methods: {
    getGenresList(allGenres) {
      this.genresList = allGenres;
    },
    startSearch(genreToSearch) {
      console.log(genreToSearch);
      this.genreToSearch = genreToSearch;
    }
  }
}
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: white;
}
header {
  height: 15vh;
}
main {
  height: 150vh;
  background-color: #1e2d3b;
}
</style>
