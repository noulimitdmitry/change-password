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

<style scoped lang="scss">
.header {
  width: 100%;
  font-family: Roboto;
}
.title {
  padding: 2rem 0;
  font-size: calc(20px + 10 * (100vw / 1230));
  @media(max-width:767px){
    font-size: calc(20px + (10 + 10 * 0.7) * ((100vw - 320px) / 1230));
    padding: 1.2rem 0;
  }
}
</style>
