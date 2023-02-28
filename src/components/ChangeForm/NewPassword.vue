<template>
    <div>
      <input type="password" :placeholder=ph v-model="newPassword" class="input-password new-password">
      <CloseEyes/>
      <OpenEyes/>
    </div>
</template>

<script>
import CloseEyes from '@/components/ChangeForm/SvgIcons/CloseEyes.vue'
import OpenEyes from '@/components/ChangeForm/SvgIcons/OpenEyes.vue'

export default {
  name: 'NewPassword',
  props: {
    ph: String
  },
  components: {
    CloseEyes,
    OpenEyes
  },
  data () {
    return {
      newPassword: ''
    }
  },
  methods: {
    changePassword () {
      // Виконайте перевірку введених даних і відправте запит на зміну пароля
      // Якщо зміна пароля успішна, скиньте форму
      this.newPassword = ''
    }
  }
}
</script>

<style scoped lang="scss">
.new-password {
}
</style>
