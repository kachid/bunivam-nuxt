<template>
  <v-dialog
    v-model="dialog"
    @click:outside="clickOutside"
    @keydown="clickOutside"
    :max-width="dialogWidth"
    overlay-opacity="0.8"
  >
    <video ref="video" controls>
      <source :src="video.src" :type="video.type" />
      Your browser doesn't support HTML5 video tag.
    </video>
  </v-dialog>
</template>

<script>
export default {
  name: 'ModelVideo',
  props: {
    video: {
      type: Object,
      default: () => ({
        src: '/video/Ракушка обзор 2(0).mp4',
        type: 'video/mp4',
        title: 'Обзор бани РАКУШКА'
      })
    },
    initialDialog: {
      type: Boolean,
      default: false
    }
  },
  data: () => ({
    dialog: false
  }),
  computed: {
    dialogWidth() {
      let result
      switch (this.$vuetify.breakpoint.name) {
        case 'xs':
        case 'sm':
          result = '100%'
          break
        case 'md':
          result = '80%'
          break
        case 'lg':
          result = '60%'
          break
        case 'xl':
          result = '50%'
      }
      return result
    }
  },
  watch: {
    initialDialog(value) {
      this.dialog = value
    }
  },
  methods: {
    clickOutside(e) {
      this.dialog = false
      this.$refs.video.pause()
      this.$emit('closeDialog')
    }
  }
}
</script>

<style scoped>
video {
  display: block;
  margin: 0 auto;
}
</style>
