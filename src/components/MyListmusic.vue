<template>
  <div>
      <MyMusic
      v-for="disch, i in dischs"
      :key="i"
      :details="disch"/>
  </div>
</template>

<script>
import axios from 'axios';
import MyMusic from '@/components/MyMusic.vue';

export default {
  name: 'MyListmusic',
  components: {
    MyMusic
  },
  data() {
    return {
      apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
      dischs: [],
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
        this.dischs = music.data;
      })
    }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
div {
    background-color: #1e2d3b;
    display: flex;
    flex-flow: row wrap;
}
</style>