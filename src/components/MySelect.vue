<template>
  <select name="genres" v-model="selectedValue" @change="$emit('search', selectedValue)">
      <option value="1">Rock</option>
      <option value="2">Pop</option>
      <option value="3">Jazz</option>
      <option value="4">Metal</option>
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
//   computed: {
//       filteredElements() {
//           if (selectedValue == "1") {
//               return
//           } else if (selectedValue == "2") {
//               return
//           } else {
//               return
//           }
//       }
//   },

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