<template>
  <div>
    <!-- <MySelect
    @search="MyElements"/> -->
    <div id="songs">
      <MyMusic
      v-for="disch, i in filtered"
      :key="i"
      :details="disch"/>
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
  data() {
    return {
      apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
      dischs: [],
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
      })
    },
    MyElements(selected) {
      console.log(selected);
      this.selected = selected
    }
  },
  computed: {
    filtered () {
      let filtered = this.dischs;
      let element  = this.selected;

      if(element === "") {
          return this.dischs
      }

      filtered = filtered.filter((item) => {
          return item.genre === this.selected
      });

      return filtered;
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