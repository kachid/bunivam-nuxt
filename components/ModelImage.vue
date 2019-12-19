<template>
  <div>
    <v-avatar @click.stop="dialog = true" class="ma-3" size="400" tile>
      <v-img :src="images[0].src" />
    </v-avatar>
    <v-dialog
      v-model="dialog"
      @click:outside="clickOutside"
      @keydown="clickOutside"
      overlay-opacity="0.8"
    >
      <v-carousel
        cycle
        height="600"
        hide-delimiter-background
        show-arrows-on-hover
      >
        <v-carousel-item
          v-for="(image, i) in images"
          :key="i"
          :src="image.src"
          contain
          reverse-transition="fade-transition"
          transition="fade-transition"
        >
        </v-carousel-item>
      </v-carousel>
    </v-dialog>
  </div>
</template>

<script>
export default {
  name: 'ModelImage',
  props: {
    images: {
      type: Array,
      default: () => [{ src: '/images/default-house.jpg', alt: 'Баня' }]
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
      this.$emit('closeDialog')
    }
  }
}
</script>

<style scoped></style>
