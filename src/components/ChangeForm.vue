<template>
  <form action="#">
    <div class="input-block">
      <input type="password" placeholder="Current password" v-model="oldPassword" class="input-password">
      <Icons/>
      <!-- <CloseEyes @click="showPassword = !showPassword" :class="{ active: showPassword }"/>
      <OpenEyes @click="showPassword = false" :class="{ active: !showPassword }"/> -->
    </div>
    <div class="input-block">
      <input type="password" placeholder="New password" v-model="newPassword" class="input-password new-password">
      <Icons/>
    </div>
    <div class="input-block">
      <input type="password" placeholder="Repeat new password" v-model="confirmPassword" class="input-password new-password">
      <!-- <CloseEyes ref="closeEyes"/> -->
      <Icons/>
    </div>
    <CustomButton  msg="Change Password"/>
  </form>
</template>

<script>
import Icons from '@/components/ChangeForm/SvgIcons/Icons.vue'
import CustomButton from '@/components/ChangeForm/CustomButton.vue'

export default {
  name: 'ChangeForm',
  components: {
    CustomButton,
    Icons
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

<style lang="scss">
.input-password {
  position: absolute;
  left: 0;
  bottom: 0.4rem;
  text-align: left;
  display: block;
  width: 100%;
  background-color: rgb(255, 255, 255);
}
</style>
