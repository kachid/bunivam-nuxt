<template>
  <article>
    <v-card>
      <div class="d-flex flex-no-wrap justify-space-between">
        <div>
          <v-card-title
            v-text="currentModel.name"
            class="headline"
          ></v-card-title>

          <v-card-subtitle v-text="currentModel.subheader"></v-card-subtitle>
        </div>

        <v-avatar class="ma-3" size="125" tile>
          <v-img :src="currentModel.images[0].src"></v-img>
        </v-avatar>
      </div>
    </v-card>
  </article>
</template>

<script>
export default {
  validate({ params }) {
    return Boolean(params.id)
  },
  data: () => ({
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
        description: `
        Терраса 1 метр с козырьком, пол: доска шип-паз, резные балясины.
        Парная: отделка вагонкой Липа Экстра, воздушный зазор, фольгированный
          утеплитель 8 мм, сухая обработанная доска 40 мм, мембрана от
          образования конденсата, имитация бруса, мягкая кровля. Дверь липа.
          Пол доска 40 мм, герметичный слив, выведенный в трубу наружу,
          утеплитель 40мм. Двухуровневый полок Липа Экстра, два декоративных
          светильника, окно, вентиляция. Печь Термофор, бак 50 л, дымоход сэндвич.
        Комната: вагонка сосна сорт АB, воздушный зазор, фольгированный
          утеплитель 8 мм, сухая обработанная доска 40 мм, мембрана от
          образования конденсата, имитация бруса, мягкая кровля. Стол, две
          скамьи сосна, вентиляция.
          Дверь липа.
          Пол: утеплитель 40 мм, пароизоляция, доска половая 40 мм шип-паз.
        Скрытая проводка со светодиодными паронепроницаемыми светильниками в каждом отделении.
        Основание: обработанная огнебиозащитой доска 50*150, половые лаги, блоки для установки.`
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

<style lang="scss" scoped></style>
