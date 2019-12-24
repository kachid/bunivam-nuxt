<template>
  <v-card :to="`/models/${model.id}`" max-width="350" height="420" nuxt hover>
    <v-card-title class="justify-center">{{ model.name }}</v-card-title>
    <v-img
      :src="model.src2"
      :srcset="model.src1"
      :alt="model.description"
      max-width="300"
      max-height="300"
    />
    <v-card-text class="text-center">от {{ model.price }} руб.</v-card-text>
  </v-card>
</template>

<script>
export default {
  props: {
    // eslint-disable-next-line vue/require-default-prop
    model: {
      type: Object
    }
  }
}
</script>

<style lang="scss" scoped></style>
