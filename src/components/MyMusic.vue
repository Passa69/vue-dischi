<template>
  <div>
      <img :src="details.poster" alt="details.title">
      <h5>{{details.title}}</h5>
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
    height: 350px;
    width: 180px;
    margin: 50px;
    background-color: #2e3a46;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;

    img {
        width: 150px;
    }

    h5 {
        margin: 10px;
    }

    p {
        color: #646466;
        font-size: 15px;
    }
}
</style>