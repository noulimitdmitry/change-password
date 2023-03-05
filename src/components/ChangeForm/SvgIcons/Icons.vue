<template>
      <CloseEyes v-show="showOpenEyes" @click="toggleEyes"/>
      <OpenEyes  v-show="showCloseEyes" @click="toggleEyes"/>
</template>

<script>

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
      showCloseEyes: true,
      showOpenEyes: false
    }
  },
  methods: {
    toggleEyes () {
      this.showCloseEyes = !this.showCloseEyes
      this.showOpenEyes = !this.showOpenEyes
    }
  }
}
</script>
