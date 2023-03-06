<template>
  <form action="#">
    <div class="input-block">
      <input placeholder="Current password" v-model="oldPassword" v-bind:type="inputType" class="input-password">
      <CloseEyes v-show="showOpenEyes" @click="toggleEyes"  v-on:click="togglePassword"/>
      <OpenEyes  v-show="showCloseEyes" @click="toggleEyes"  v-on:click="togglePassword"/>
    </div>
    <div class="input-block">
      <input placeholder="New password" v-model="newPassword" v-bind:type="inputType" class="input-password">
      <CloseEyes v-show="showOpenEyes" @click="toggleEyes"  v-on:click="togglePassword"/>
      <OpenEyes  v-show="showCloseEyes" @click="toggleEyes"  v-on:click="togglePassword"/>
    </div>
    <div class="input-block">
      <input placeholder="Repeat new password" v-model="confirmPassword" v-bind:type="inputType" class="input-password">
      <CloseEyes v-show="showOpenEyes" @click="toggleEyes"  v-on:click="togglePassword"/>
      <OpenEyes  v-show="showCloseEyes" @click="toggleEyes"  v-on:click="togglePassword"/>
    </div>
    <button type="submit" class="button" @click="changePassword">Change Password</button>
  </form>
</template>

<script>
import axios from 'axios'
import CloseEyes from '@/components/ChangeForm/SvgIcons/CloseEyes.vue'
import OpenEyes from '@/components/ChangeForm/SvgIcons/OpenEyes.vue'

export default {
  name: 'ChangeForm',
  components: {
    CloseEyes,
    OpenEyes
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
      const passwordRegex = /^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)[a-zA-Z\d]{8,}$/
      if (!passwordRegex.test(this.newPassword)) {
        alert('Password must be at least 8 characters long and contain at least one lowercase letter, one uppercase letter, and one number')
        return
      }
      if (!passwordRegex.test(this.confirmNewPassword)) {
        alert('Please enter a valid confirmation password')
        return
      }
      const data = {
        currentPassword: this.currentPassword,
        newPassword: this.newPassword,
        confirmPassword: this.confirmNewPassword
      }
      axios.post('/change-password', data).then(response => {
        // Processing the response from the server
        console.log(response.data)
        alert('Password successfully changed')
        this.currentPassword = ''
        this.newPassword = ''
        this.confirmNewPassword = ''
      }).catch(error => {
        // Error handling
        console.error(error)
      })
    },
    toggleEyes () {
      this.showCloseEyes = !this.showCloseEyes
      this.showOpenEyes = !this.showOpenEyes
    },
    togglePassword () {
      this.showPassword = !this.showPassword
      if (this.showPassword) {
        this.inputType = 'text'
      } else {
        this.inputType = 'password'
      }
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
.input-password {
  position: absolute;
  left: 0;
  bottom: 0.4rem;
  text-align: left;
  display: block;
  width: 100%;
  background-color: rgb(255, 255, 255);
}
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
