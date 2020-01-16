<template>
  <v-row>
    <v-col v-for="model in modelList" :key="model.id">
      <app-model-preview :model="model" />
    </v-col>
  </v-row>
</template>

<script>
import AppModelPreview from '@/components/ModelPreview'

import { modelList } from '@/data'

export default {
  components: {
    AppModelPreview
  },
  data: () => ({
    modelList
  })
}
</script>
