<template>
<main class="main">
  <AboutUser userId="user ID" email="example@gmail.com" />
  <ChangeForm />
</main>
</template>

<script>
import AboutUser from '@/components/AboutUser.vue'
import ChangeForm from '@/components/ChangeForm.vue'

export default {
  name: 'MainField',
  components: {
    AboutUser,
    ChangeForm
  }
}
</script>

<style scoped lang="scss">
.main{
  background-color: rgb(255, 255, 255);
  padding-top: 6rem;
  @media(max-width:767px){
    padding-top: 3rem;
  }
}
</style>
