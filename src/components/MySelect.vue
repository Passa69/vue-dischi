<template>
  <select name="genres" v-model="selectedValue" @change="$emit('search', selectedValue)">
      <option value="Rock">Rock</option>
      <option value="Pop">Pop</option>
      <option value="Jazz">Jazz</option>
      <option value="Metal">Metal</option>
  </select>
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
select {
    padding: 10px 25px;
    margin-top: 20px;
    font-size: 15px;
    color: white;
    background-color: #2e3a46;
    border-color: #2e3a46;
    border-radius: 15px;
}
</style>