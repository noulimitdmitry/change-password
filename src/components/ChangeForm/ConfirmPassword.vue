<template>
    <div>
      <input type="password" :placeholder=ph v-model="confirmPassword" class="input-password new-password">
      <CloseEyes/>
      <OpenEyes/>
    </div>
</template>

<script>
import CloseEyes from '@/components/ChangeForm/SvgIcons/CloseEyes.vue'
import OpenEyes from '@/components/ChangeForm/SvgIcons/OpenEyes.vue'

export default {
  name: 'ConfirmPassword',
  props: {
    ph: String
  },
  components: {
    CloseEyes,
    OpenEyes
  },
  data () {
    return {
      confirmPassword: ''
    }
  },
  methods: {
    changePassword () {
      // Виконайте перевірку введених даних і відправте запит на зміну пароля
      // Якщо зміна пароля успішна, скиньте форму
      this.confirmPassword = ''
    }
  }
}
</script>

<style scoped lang="scss">
.new-password {
}
</style>
