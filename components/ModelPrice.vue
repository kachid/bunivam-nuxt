<template>
  <v-list shaped expand>
    <v-subheader>ЦЕНА</v-subheader>
    <v-list-item-group v-model="item" color="primary">
      <v-list-item v-for="(item, i) in price" :key="i">
        <v-list-item-content>
          <v-list-item-title
            >{{ item.size }} - {{ item.cost }}</v-list-item-title
          >
        </v-list-item-content>
      </v-list-item>
    </v-list-item-group>
  </v-list>
</template>

<script>
export default {
  name: 'ModelPrice',
  props: {
    // eslint-disable-next-line vue/require-default-prop
    price: {
      type: Array
    }
  },
  data: () => ({
    item: 1
  })
}
</script>

<style scoped></style>
