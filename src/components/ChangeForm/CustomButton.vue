<template>
  <button type="submit" class="button" @click="changePassword">{{msg}}</button>
</template>

<script>
// import axios from 'axios'

export default {
  name: 'CustomButton',
  props: {
    buttonText: {
      type: String,
      required: true
    },
    msg: String
  }
  // methods: {
  //   changePassword () {
  //    axios.post('/api/change-password')
  //         .then(response => {
  //           // дії, що виконуються після успішного запиту
  //         })
  //         .catch(error => {
  //           // дії, що виконуються в разі помилки запиту
  //         })
  //   }
  // }
}
</script>

<style scoped lang="scss">
.button{
  background-color:rgb(71, 98, 91);
  color: rgb(70, 227, 141);
  margin-top: 3rem;
  width: 30%;
  height: 2.5rem;
  border-radius: 5px;
  opacity: 40%;
  font-size: calc(12px + 4 * (100vw / 1280));
  @media(max-width:767px){
    width: 40%;
    font-size: calc(12px + (4 + 4 * 0.7) * ((100vw - 320px) / 1280));
  }
}
</style>
