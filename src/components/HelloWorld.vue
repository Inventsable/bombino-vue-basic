<template>
  <div class="centered">
    <img alt="Vue logo" src="../assets/logo.png" />
    <h1>{{ msg }}</h1>
  </div>
</template> 

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.centered {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}
</style>
