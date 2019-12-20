<template>
  <header>
    <h2>Модели</h2>
    <nuxt-link
      :to="`/models/${model.id}`"
      v-for="model in modelList"
      :key="model.id"
    >
      {{ model.name }}
      <div class="wrapper_nav-img">
        <picture>
          <source :srcset="model.src1" />
          <img :src="model.src2" :alt="model.description" />
        </picture>
      </div>
      <span>от {{ model.price }} руб.</span>
    </nuxt-link>
  </header>
</template>

<script>
export default {
  data: () => ({
    modelList: [
      {
        id: 1,
        name: 'Ракушка',
        description: 'Ракушка',
        price: 139000,
        src1: '/images/rakush_card_1_small.png',
        src2: '/images/rakush_card_1_small.webp'
      },
      {
        id: 2,
        name: 'Скандинавия',
        description: 'Скандинавия',
        price: 195000,
        src1: '/images/scand_card_small.png',
        src2: '/images/scand_card_small.webp'
      },
      {
        id: 3,
        name: 'Каравелла',
        description: 'Каравелла',
        price: 129000,
        src1: '/images/Каравелла_card_small.png',
        src2: '/images/Каравелла_card_small.webp'
      },
      {
        id: 4,
        name: 'Радуга',
        description: 'Радуга',
        price: 74000,
        src1: './images/1%20Радуга.jpg',
        src2: './images/1%20Радуга.jpg'
      }
    ]
  })
}
</script>
