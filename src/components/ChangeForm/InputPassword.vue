<template>
      <input :placeholder="ph" :v-model="vm" v-bind:type="inputType" class="input-password">
      <CloseEyes v-show="showOpenEyes" @click="toggleEyes"  v-on:click="togglePassword"/>
      <OpenEyes  v-show="showCloseEyes" @click="toggleEyes"  v-on:click="togglePassword"/>
</template>

<script>

import CloseEyes from '@/components/ChangeForm/SvgIcons/CloseEyes.vue'
import OpenEyes from '@/components/ChangeForm/SvgIcons/OpenEyes.vue'

export default {
  name: 'InputPassword',
  props: {
    ph: String,
    vm: String
  },
  components: {
    CloseEyes,
    OpenEyes
  },
  data () {
    return {
      inputType: 'password',
      showCloseEyes: false,
      showOpenEyes: true
    }
  },
  methods: {
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
  }
}
</script>

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
