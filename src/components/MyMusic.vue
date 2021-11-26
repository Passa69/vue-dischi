<template>
  <div>
      <img :src="details.poster" alt="details.title">
      <h3>{{details.title}}</h3>
      <p>{{details.author}}</p>
      <p>{{details.year}}</p>
  </div>
</template>

<script>
export default {
  name: 'MyMusic',
  props: {
      details: Object
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
div {
    height: 400px;
    width: 230px;
    margin: 50px 20px 20px 100px;
    background-color: #2e3a46;
    display: flex;
    flex-direction: column;
    align-content: center;

    img {
        margin-top: 30px;
        width: 180px;
    }

    h3 {
        margin: 10px 0;
    }

    p {
        color: #646466;
        font-size: 15px;
    }
}
</style>