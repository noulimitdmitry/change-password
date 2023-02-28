<template>
  <router-view />
</template>

<style lang="scss">

@import url(https://fonts.googleapis.com/css?family=Poppins:regular,500,600&display=swap);

$containerWidth : 1230px;
$wrapperBackground : #f8f7f5;
$color: rgb(14, 62, 6);

body, html, #app, .change-password, .wrapper{
  height: 100%;
  font-size: 16px;
}

#app {
  height: 100%;
  font-family: Poppins;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
}

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

input:focus {
  outline: none;
}

body{
  line-height: 1;
}

.wrapper{
  background-color: $wrapperBackground;
  color: $color;
  padding: 0 1.5rem;
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

</style>
