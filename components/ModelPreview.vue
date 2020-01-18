<template>
  <v-card :to="`/models/${model.id}`" max-width="350" height="420" nuxt hover>
    <v-card-title class="justify-center">{{ model.name }}</v-card-title>
    <v-card-subtitle class="text-center"
      >от {{ model.price }} руб.</v-card-subtitle
    >
    <v-img
      :src="model.src2"
      :srcset="model.src1"
      :alt="model.description"
      max-width="350"
      max-height="300"
    />
  </v-card>
</template>

<script>
export default {
  name: 'ModelPreview',
  props: {
    // eslint-disable-next-line vue/require-default-prop
    model: {
      type: Object
    }
  }
}
</script>
