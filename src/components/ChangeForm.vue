<template>
  <form action="#">
    <CurrentPassword class="input-block"/>
    <NewPassword class="input-block" ph="New password"/>
    <ConfirmPassword class="input-block" ph="Repeat new password"/>
    <CustomButton  msg="Change Password"/>
  </form>
</template>

<script>
import CurrentPassword from '@/components/ChangeForm/CurrentPassword.vue'
import NewPassword from '@/components/ChangeForm/NewPassword.vue'
import ConfirmPassword from '@/components/ChangeForm/ConfirmPassword.vue'
import CustomButton from '@/components/ChangeForm/CustomButton.vue'

export default {
  name: 'ChangeForm',
  components: {
    CurrentPassword,
    NewPassword,
    ConfirmPassword,
    CustomButton
  },
  data () {
    return {
      currentPassword: '',
      newPassword: '',
      confirmNewPassword: ''
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

<style lang="scss">
.input-password{
  position: absolute;
  left: 0;
  bottom: 0.4rem;
  text-align: left;
  display: block;
  width: 100%;
  background-color: rgb(255, 255, 255);
}
</style>
