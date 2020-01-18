<template>
  <v-list-group no-action value="expand">
    <template v-slot:activator>
      <v-list-item-content>
        <v-list-item-title>{{ subtitle }}</v-list-item-title>
      </v-list-item-content>
    </template>

    <v-list-item
      v-for="(item, i) in array"
      :key="i"
      @click="$emit('selectedItem', item.id)"
    >
      <v-list-item-title v-text="item.text" />
      <v-list-item-action>
        <v-list-item-action-text v-text="item.price" />
      </v-list-item-action>
    </v-list-item>
  </v-list-group>
</template>

<script>
export default {
  name: 'AdditionsListGroup',
  props: {
    subtitle: {
      type: String,
      default: ''
    },
    // eslint-disable-next-line vue/require-default-prop
    array: {
      type: Array
    },
    expand: {
      type: Boolean,
      default: false
    }
  },
  data: () => ({
    selected: ''
  })
}
</script>
