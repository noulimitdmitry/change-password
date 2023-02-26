<template>
  <router-view />
</template>

<style lang="scss">
#app {
  height: 100%;
  font-family: Poppins;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
}
@import url(https://fonts.googleapis.com/css?family=Poppins:regular,500,600&display=swap);

$containerWidth : 1230px;

*, *::before, *::after{
  padding: 0;
  margin: 0;
  border: none;
  box-sizing: border-box;
}
li {
  list-style: none;
  color: inherit;
}

a{
  text-decoration: none;
  color: inherit;
}

body, html, #app, .change-password, .wrapper{
  height: 100%;
}

body{
  line-height: 1;
}

.container{
  max-width: $containerWidth;
  margin: 0 auto;
  overflow: hidden;
  min-height: 100%;
  display: flex;
  flex-direction: column;
}

main{
flex: 1 0 auto;
}

.wrapper{
  background-color: #f8f7f5;
  color:  rgb(14, 62, 6);
}

</style>
