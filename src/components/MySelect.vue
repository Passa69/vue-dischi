<template>
  <select name="genere" id="">
      <option value="">All</option>
      <option value="">Rock</option>
      <option value="">Pop</option>
      <option value="">Metal</option>
  </select>
</template>

<script>
export default {
  name: 'MySelect',

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