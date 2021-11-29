<template>
  <header>
    <p>&#9679;</p>
  </header>
</template>

<script>
export default {
  name: 'MyHeader',

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
</style>
