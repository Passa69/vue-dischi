<template>
  <header>
    <p>&#9679;</p>

    <select 
        name="genres" 
        v-model="selectedValue" 
        @change="$emit('cheangedGenre', selectedValue)">

      <!-- <option value="Rock">Rock</option>
      <option value="Pop">Pop</option>
      <option value="Jazz">Jazz</option>
      <option value="Metal">Metal</option> -->

      <option value="">Seleziona un genere</option>
      <option
          v-for="(genre, index) in genres"
          :key="index"
          :value="genre">
          {{ genre }}
          </option>
    </select>
  </header>
  
</template>

<script>
export default {
  name: 'MySelect',
  props: {
    genres: Array,
  },
  data() {
      return {
          selectedValue: "",
      }
  },

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
header {
  background-color: #2e3a46;
  position: relative;

  p {
    color: #1ed55f;
    font-size: 80px;
    position: absolute;
    top: 10px;
    left: 10px;
  }
}

select {
    float: right;
    padding: 10px 30px;
    margin: 30px 20px 0 0 ;
    font-size: 15px;
    background-color: white;
    border-color: #2e3a46;
    border-radius: 15px;
}
</style>