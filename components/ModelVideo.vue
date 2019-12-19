<template>
  <v-dialog
    v-model="dialog"
    @click:outside="clickOutside"
    @keydown="clickOutside"
    max-width="80%"
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
  max-width: 80%;
}
</style>
