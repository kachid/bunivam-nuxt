<template>
  <v-row justify="center">
    <v-col cols="12" lg="9">
      <v-card>
        <v-card-title>ОТЗЫВЫ</v-card-title>
        <v-row>
          <v-col v-for="(src, i) in srcVideo" :key="i" cols="12" lg="6">
            <v-card outlined>
              <v-row justify="center" align="center">
                <v-col>
                  <video controls="controls" class="text-center">
                    <source :src="src" :type="typeVideo" :onclick="yaCounter" />
                    Элемент video не поддерживается вашим браузером.
                  </video>
                </v-col>
              </v-row>
            </v-card>
          </v-col>
        </v-row>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  data: () => ({
    srcVideo: [
      '/video/review4.mp4',
      '/video/review3.mp4',
      '/video/review5.mp4',
      '/video/review1.mp4',
      '/video/review2.mp4',
      '/video/review6.mp4',
      '/video/review7.mp4',
      '/video/review8.mp4',
      '/video/review9.mp4',
      '/video/reviewA.mp4'
    ],
    typeVideo: 'video/mp4',
    yaCounter: "yaCounter54743977.reachGoal('show_review'); return true;"
  })
}
</script>

<style lang="scss" scoped>
video {
  max-width: 100%;
  margin: auto;
}
</style>
