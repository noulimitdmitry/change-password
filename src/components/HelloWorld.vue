<template>
  <div class="header">
    <h1 class="title">{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.header {
  width: 100%;
  font-family: Roboto;
}
.title {
  padding: 30px 0;
  font-size: 2.2rem;
}
</style>
