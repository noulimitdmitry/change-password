<template>
  <div class="change-password">
    <div class="wrapper">
      <div class="container">
        <HelloWorld msg="Change password" />
        <MainField />
      </div>
    </div>
  </div>
</template>

<script>
import HelloWorld from '@/components/HelloWorld.vue'
import MainField from '@/components/MainField.vue'

export default {
  name: 'ChangePassword',
  components: {
    HelloWorld,
    MainField
  }
}
</script>
