<template>
  <div>
      <MyMusic/>
  </div>
</template>

<script>
import MyMusic from '@/components/MyMusic.vue';

export default {
  name: 'MyListmusic',
  components: {
    MyMusic
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