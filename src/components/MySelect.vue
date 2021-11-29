<template>
  <select name="genres" v-model="selectedValue" @change="MyElements">
      <option value="1">Rock</option>
      <option value="2">Pop</option>
      <option value="3">Metal</option>
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
  computed: {
      filteredElements() {
          if (selectedValue == "1") {
              return
          } else if (selectedValue == "2") {
              return
          } else {
              return
          }
      }
  },
  methods: {
      MyElements() {
          console.log('il valore è', this.selectedValue);
      }
  }

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