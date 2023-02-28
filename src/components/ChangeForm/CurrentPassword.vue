<template>
    <div>
      <input type="password" placeholder="Current password" v-model="oldPassword" class="input-password">
      <CloseEyes/>
      <OpenEyes/>
    </div>
</template>

<script>
import CloseEyes from '@/components/ChangeForm/SvgIcons/CloseEyes.vue'
import OpenEyes from '@/components/ChangeForm/SvgIcons/OpenEyes.vue'

export default {
  name: 'CurrentPassword',
  components: {
    OpenEyes,
    CloseEyes
  },
  data () {
    return {
      oldPassword: ''
    }
  },
  methods: {
    changePassword () {
      // Виконайте перевірку введених даних і відправте запит на зміну пароля
      // Якщо зміна пароля успішна, скиньте форму
      this.oldPassword = ''
    }
  }
}
</script>
