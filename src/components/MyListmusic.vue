<template>
  <div>
    <MySelect
    @search="MyElements"/>
    <div id="songs">
      <MyMusic
      v-for="disch, i in filteredElements"
      :key="i"
      :details="disch"/>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import MyMusic from '@/components/MyMusic.vue';
import MySelect from '@/components/MySelect.vue';

export default {
  name: 'MyListmusic',
  components: {
    MyMusic,
    MySelect
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
  computed: {
      filteredElements() {
          if (selected === "0") {
            return this.dischs
          } else if (selected === "1") {
              return this.dischs.genre= "Rock"
          } else if (selected === "2") {
              return this.dischs.genre= "Pop"
          } else if (selected === "3"){
              return this.dischs.genre= "Jazz"
          } else if (selected === "4"){
              return this.dischs.genre= "Metal"
          }
      }
  },
  methods: {
    getMusic() {
      axios
      .get(this.apiUrl)
      .then((music) => {
        this.dischs = music.data.response;
      })
    },
    MyElements(selected) {
        console.log(selected);
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