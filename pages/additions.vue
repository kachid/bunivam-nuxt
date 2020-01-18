<template>
  <v-row>
    <v-col>
      <v-card width="400">
        <v-list>
          <app-additions-list-group
            v-for="(subtitle, i) in subtitles"
            :key="i"
            :subtitle="subtitle.name"
            :array="subtitle.array"
            :expand="subtitles.expand"
            @selectedItem="currentItemID = $event"
          />
        </v-list>
        <v-card-text>{{ currentItemID }}</v-card-text>
      </v-card>
    </v-col>
    <v-col cols="12" lg="8">
      <v-carousel v-model="currentItemID">
        <v-carousel-item
          v-for="image in additionsImges"
          :key="image.id"
          :src="image.src"
          contain
        >
        </v-carousel-item>
      </v-carousel>
    </v-col>
  </v-row>
</template>

<script>
import AppAdditionsListGroup from '@/components/AdditionsListGroup'
import { additions } from '@/data'

export default {
  name: 'Additions',
  components: {
    AppAdditionsListGroup
  },
  data: () => ({
    currentItemID: '',
    additions,
    steamRoomID: [10, 11, 19],
    washingRoomID: [1, 6, 7, 13, 14],
    restRoomID: [2, 8, 9, 22],
    otherItemsID: [3, 4, 5, 12, 15, 16, 17, 18, 20, 21]
  }),
  computed: {
    steamRoom() {
      return this.filterBySubtitles(this.steamRoomID)
    },
    washingRoom() {
      return this.filterBySubtitles(this.washingRoomID)
    },
    restRoom() {
      return this.filterBySubtitles(this.restRoomID)
    },
    otherItems() {
      return this.filterBySubtitles(this.otherItemsID)
    },
    subtitles() {
      return [
        { name: 'Парная', array: this.steamRoom, expand: true },
        { name: 'Мойка', array: this.washingRoom },
        { name: 'Комната отдыха', array: this.restRoom },
        { name: 'Прочее', array: this.otherItems }
      ]
    },
    additionsImges() {
      return this.additions.map((item) => {
        item.src = item.src || '/images/default-house.jpg'
        return item
      })
    }
  },
  methods: {
    filterBySubtitles(keyList) {
      return this.additions.filter((item) => keyList.includes(item.id))
    }
  }
}
</script>
