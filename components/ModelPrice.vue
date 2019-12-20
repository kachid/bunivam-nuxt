<template>
  <v-list shaped elevation="2" expand>
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
