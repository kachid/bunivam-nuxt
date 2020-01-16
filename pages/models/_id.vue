<template>
  <article>
    <v-card>
      <div class="d-flex flex-wrap justify-space-around align-center">
        <v-card-title v-text="currentModel.name" class="headline" />
        <div>{{ currentModel.subheader }}</div>
      </div>
      <v-row>
        <v-col>
          <v-card flat>
            <AppModelImage
              :images="currentModel.images"
              :initialDialog="openCarousel"
              @closeDialog="openCarousel = false"
            />
            <AppModelVideo
              :video="currentModel.video"
              :initialDialog="dialogVideo"
              @closeDialog="dialogVideo = false"
            />
            <v-card-actions>
              <v-btn @click="openCarousel = true">photo</v-btn>
              <v-btn @click.stop="dialogVideo = true">video</v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
        <v-col>
          <AppModelPrice :price="currentModel.price" />
        </v-col>
        <v-col cols="12" lg="6">
          <v-card-text>
            <div class="subtitle-1">МАТЕРИАЛЫ И КОМПЛЕКТАЦИЯ</div>
            <p v-for="(paragraf, i) in currentModel.description" :key="i">
              {{ paragraf.title }} {{ paragraf.content }}
            </p>
          </v-card-text>
        </v-col>
      </v-row>
    </v-card>
  </article>
</template>

<script>
import AppModelImage from '@/components/ModelImage'
import AppModelVideo from '@/components/ModelVideo'
import AppModelPrice from '@/components/ModelPrice'

import { models } from '@/data'

export default {
  components: {
    AppModelImage,
    AppModelVideo,
    AppModelPrice
  },
  validate({ params }) {
    return Boolean(params.id)
  },
  data: () => ({
    openCarousel: false,
    dialogVideo: false,
    models
  }),
  computed: {
    currentModel() {
      return this.models.find(({ id }) => id === this.id)
    }
  },
  asyncData({ params }) {
    const id = Number(params.id)
    return { id }
  }
}
</script>
