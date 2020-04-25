<template>
  <div class="centered">
    <img alt="Vue logo" src="../assets/logo.png" />
    <h1 class="centered">{{ msg }}</h1>
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
  width: 100%;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}
</style>
