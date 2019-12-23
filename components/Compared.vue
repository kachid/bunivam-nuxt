<template>
  <v-card class="mx-auto" shaped>
    <v-list>
      <v-subheader>{{ distinction.header }}</v-subheader>
      <v-list-item-group v-model="item" color="primary">
        <v-list-item>
          <v-list-item-icon>
            <v-icon v-text="icons.our" />
          </v-list-item-icon>
          <v-list-item-content>
            {{ distinction.our }}
          </v-list-item-content>
        </v-list-item>
        <v-list-item>
          <v-list-item-icon>
            <v-icon v-text="icons.other" />
          </v-list-item-icon>
          <v-list-item-content>
            {{ distinction.other }}
          </v-list-item-content>
        </v-list-item>
      </v-list-item-group>
    </v-list>
  </v-card>
</template>

<script>
export default {
  name: 'Compared',
  props: {
    // eslint-disable-next-line vue/require-default-prop
    distinction: {
      type: Object
    }
  },
  data: () => ({
    item: 0,
    icons: {
      our: 'mdi-thumb-up-outline',
      other: 'mdi-thumb-down'
    }
  })
}
</script>

<style scoped />
