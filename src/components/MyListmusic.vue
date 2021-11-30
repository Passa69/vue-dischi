<template>
  <div>
    <!-- <MySelect
    @search="MyElements"/> -->
    <div id="songs">
      <MyMusic
      v-for="(dischItem, i) in filtered"
      :key="i"
      :details="dischItem"/>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import MyMusic from '@/components/MyMusic.vue';
// import MySelect from '@/components/MySelect.vue';

export default {
  name: 'MyListmusic',
  components: {
    MyMusic,
    // MySelect
  },
  props: {
    selectedGenre: String,
  },
  data() {
    return {
      apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
      dischs: [],
      genres: [],
      selected: ""
    }
  },
  created() {
    this.getMusic();
  },
  methods: {
    getMusic() {
    axios
    .get(this.apiUrl)
    .then((music) => {
      this.dischs = music.data.response;

      this.dischs.forEach((dischItem) => {
        if (!this.genres.includes(dischItem.genre)) {
            this.genres.push(dischItem.genre);
        }
      });

      this.$emit("genresReady", this.genre);
      })
    .catch((error) => {
      console.log("l'errore è: ", error);
      })
    },
    MyElements(selected) {
      console.log(selected);
      this.selected = selected
    }
  },
  computed: {
    filtered () {
      if(this.selectedGenre === "") {
          return this.dischs
      }

      return this.dischs.filter(
        (item) => item.genre === this.selectedGenre
      );
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
#songs {
    padding: 20px 50px;
    display: flex;
    flex-flow: row wrap;
}
</style>