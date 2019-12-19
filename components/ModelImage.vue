<template>
  <div>
    <v-avatar @click.stop="dialog = true" class="ma-3" size="400" tile>
      <v-img :src="images[0].src" />
    </v-avatar>
    <v-dialog
      v-model="dialog"
      @click:outside="clickOutside"
      @keydown="clickOutside"
      :max-width="dialogWidth"
      overlay-opacity="0.8"
    >
      <v-carousel
        :height="carouselHeight"
        cycle
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
          <v-list-item color="rgba(0, 0, 0, .4)" dark>
            <v-list-item-content>
              <v-list-item-title class="title">
                {{ image.alt }}
              </v-list-item-title>
              <v-list-item-subtitle>
                {{ currentBreackpoint }} - {{ carouselHeight }}
              </v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
        </v-carousel-item>
      </v-carousel>
    </v-dialog>
  </div>
</template>

<script>
export default {
  name: 'ModelImage',
  mounted() {
    console.log(this.$vuetify.breakpoint)
  },
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
    },
    carouselHeight() {
      const height = this.$vuetify.breakpoint.height
      const width = this.$vuetify.breakpoint.width
      let result
      switch (this.$vuetify.breakpoint.name) {
        case 'xs':
        case 'sm':
          result = height < width ? height : '300'
          break
        case 'md':
          result = '500'
          break
        case 'lg':
          result = '600'
          break
        case 'xl':
          result = '700'
      }
      return result
    },
    currentBreackpoint() {
      return `h:${this.$vuetify.breakpoint.height} - w:${this.$vuetify.breakpoint.width}`
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
      this.$emit('closeDialog')
    }
  }
}
</script>

<style scoped></style>
