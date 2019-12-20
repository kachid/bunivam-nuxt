<template>
  <article>
    <v-card>
      <div class="d-flex justify-space-around align-center">
        <v-card-title v-text="currentModel.name" class="headline" />
        <div>{{ currentModel.subheader }}</div>
      </div>

      <div class="d-flex">
        <v-card>
          <AppModelImage
            :images="currentModel.images"
            :initialDialog="openCarousel"
            @closeDialog="openCarousel = false"
          />
          <AppModelVideo
            :video="currentModel.video"
            :initialDialog="dialogVideo"
            @closeDialog="dialogVideo = false"
          />
          <v-card-actions>
            <v-btn @click="openCarousel = true">photo</v-btn>
            <v-btn @click.stop="dialogVideo = true">video</v-btn>
          </v-card-actions>
          <AppModelPrice :price="currentModel.price" />
        </v-card>

        <v-card-text>
          <div class="subtitle-1">МАТЕРИАЛЫ И КОМПЛЕКТАЦИЯ</div>
          <p v-for="(paragraf, i) in currentModel.description" :key="i">
            {{ paragraf.title }} {{ paragraf.content }}
          </p>
        </v-card-text>
      </div>
    </v-card>
  </article>
</template>

<script>
import AppModelImage from '@/components/ModelImage'
import AppModelVideo from '@/components/ModelVideo'
import AppModelPrice from '@/components/ModelPrice'

export default {
  components: {
    AppModelImage,
    AppModelVideo,
    AppModelPrice
  },
  validate({ params }) {
    return Boolean(params.id)
  },
  data: () => ({
    openCarousel: false,
    dialogVideo: false,
    models: [
      {
        id: 1,
        name: 'РАКУШКА',
        subheader: 'Комната + Парная + Терраса',
        images: [
          {
            src: '/images/rakushka/1 Ракушка 1.webp',
            alt: 'РАКУШКА'
          },
          {
            src: '/images/rakushka/2 Ракушка цех.webp',
            alt: 'Ракушка цех'
          },
          {
            src: '/images/rakushka/3 Ракушка 3.webp',
            alt: 'Ракушка'
          },
          {
            src: '/images/rakushka/4 Комната ракушка .webp',
            alt: 'Комната'
          },
          {
            src: '/images/rakushka/5 Ракушка комн .webp',
            alt: 'Комната с табуретом'
          },
          {
            src: '/images/rakushka/6 Ракушка комната печь стекл дверь.webp',
            alt: 'комната печь стекл дверь'
          },
          {
            src: '/images/rakushka/7 Парилка Ракушка.webp',
            alt: 'Парилка'
          },
          {
            src: '/images/rakushka/8 Печь в парилке.webp',
            alt: 'Парилка'
          },
          {
            src: '/images/rakushka/9 Ракушка доставка.webp',
            alt: 'доставка'
          }
        ],
        video: {
          src: '/video/Ракушка обзор 2(0).mp4',
          type: 'video/mp4',
          title: 'Обзор бани РАКУШКА'
        },
        price: [
          {
            size: '3 x 2,4 м',
            cost: 139000
          },
          {
            size: '4 x 2,4 м',
            cost: 169000
          },
          {
            size: '5 x 2,4 м',
            cost: 190000
          },
          {
            size: '6 x 2,4 м',
            cost: 205000
          }
        ],
        description: [
          {
            title: '',
            content:
              'Терраса 1 метр с козырьком, пол: доска шип-паз, резные балясины.'
          },
          {
            title: 'Парная:',
            content:
              'отделка вагонкой Липа Экстра, воздушный зазор, фольгированный утеплитель 8 мм, сухая обработанная доска 40 мм, мембрана от образования конденсата, имитация бруса, мягкая кровля. Дверь липа. Пол доска 40 мм, герметичный слив, выведенный в трубу наружу, утеплитель 40мм. Двухуровневый полок Липа Экстра, два декоративных светильника, окно, вентиляция. Печь Термофор, бак 50 л, дымоход сэндвич.'
          },
          {
            title: 'Комната:',
            content:
              'вагонка сосна сорт АB, воздушный зазор, фольгированный утеплитель 8 мм, сухая обработанная доска 40 мм, мембрана от образования конденсата, имитация бруса, мягкая кровля. Стол, две скамьи сосна, вентиляция. Дверь липа. Пол: утеплитель 40 мм, пароизоляция, доска половая 40 мм шип-паз.'
          },
          {
            title: '',
            content:
              'Скрытая проводка со светодиодными паронепроницаемыми светильниками в каждом отделении.'
          },
          {
            title: 'Основание:',
            content:
              'обработанная огнебиозащитой доска 50*150, половые лаги, блоки для установки.'
          }
        ]
      }
    ]
  }),
  computed: {
    currentModel() {
      return this.models.find(({ id }) => id === this.id)
    }
  },
  asyncData({ params }) {
    const id = Number(params.id)
    return { id }
  }
}
</script>
