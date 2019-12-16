<template>
  <section id="reviews" class="grand_block">
    <h2>ОТЗЫВЫ</h2>
    <div class="wrap_reviews">
      <video v-for="(src, i) in srcVideo" :key="i" controls="controls">
        <source :src="src" :type="typeVideo" :onclick="yaCounter" />
        Элемент video не поддерживается вашим браузером.
      </video>
    </div>
  </section>
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

<style lang="scss" scoped></style>
