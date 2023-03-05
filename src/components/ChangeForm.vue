<template>
  <form action="#">
    <div class="input-block">
      <InputPassword ph="Current password" vm="oldPassword"/>
    </div>
    <div class="input-block">
      <InputPassword ph="New password" vm="newPassword"/>
    </div>
    <div class="input-block">
      <!-- <CloseEyes ref="closeEyes"/> -->
      <InputPassword ph="Repeat new password" vm="confirmPassword" />
    </div>
    <CustomButton  msg="Change Password"/>
  </form>
</template>

<script>
import InputPassword from '@/components/ChangeForm/InputPassword.vue'
import CustomButton from '@/components/ChangeForm/CustomButton.vue'

export default {
  name: 'ChangeForm',
  components: {
    CustomButton,
    InputPassword
  },
  data () {
    return {
      currentPassword: '',
      newPassword: '',
      confirmNewPassword: '',
      showPassword: false,
      showCloseEyes: true,
      showOpenEyes: false
    }
  },
  methods: {
    async changePassword () {
      if (this.newPassword !== this.confirmNewPassword) {
        alert('Passwords do not match')
        return
      }
      // Here you would typically send an AJAX request to the server to change the password
      // using the currentPassword and newPassword values
      alert('Password successfully changed')
      this.currentPassword = ''
      this.newPassword = ''
      this.confirmNewPassword = ''
    },
    toggleEyes () {
      this.showCloseEyes = !this.showCloseEyes
      this.showOpenEyes = !this.showOpenEyes
    }
  },
  computed: {
    inputType () {
      return this.showPassword ? 'text' : 'password'
    }
  }
}

</script>

<style scoped lang="scss">

form {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.input-block{
  position: relative;
  border-bottom: 1px solid black;
  width: 35%;
  height: 4rem;
  @media(max-width:767px){
    width: 45%;
    height: 3rem;
  }
}
</style>
