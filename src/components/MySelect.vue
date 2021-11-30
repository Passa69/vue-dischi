<template>
  <header>
    <p>&#9679;</p>

    <select name="genres" v-model="selectedValue" @change="$emit('search', selectedValue)">
      <option value="Rock">Rock</option>
      <option value="Pop">Pop</option>
      <option value="Jazz">Jazz</option>
      <option value="Metal">Metal</option>
    </select>
  </header>
  
</template>

<script>
export default {
  name: 'MySelect',

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