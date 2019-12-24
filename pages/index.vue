<template>
  <div class="wrapper_main background">
    <h1 class="h1">Бани от компании “SRUBOFF” в Екатеринбурге</h1>
    <div class="logo">
      <img src="/images/logo.png" alt="logo" />
    </div>
    <p class="h2">Всегда рядом с вами<sup>*</sup></p>
    <a class="tel1 text_right" href="tel:+73433833450">
      Телефон: 8 (343) 383-34-50
    </a>
    <a class="tel2 text_right" href="tel:+79221468521">
      WhatsApp: +7 (922) 146-85-21
    </a>
    <div class="text">
      <p class="text_center"><b>Здравствуйте, друзья!</b></p>
      <p>
        Предлагаем вам готовые бани под ключ, с оригинальным дизайном,
        построенные с соблюдением СНиП. Наши бани не рассыхаются и не гниют.
      </p>
      <p>
        <a href="#map">Приглашаем посетить наше производство</a>
        , всё посмотрите сами.
      </p>
      <p class="text_right it_bold">
        <sup>*</sup>для установки бани не требуется фундамент
      </p>
    </div>
  </div>
</template>

<script>
export default {
  components: {},
  data: () => ({
    items: [
      {
        color: '#1F7087',
        src: 'https://cdn.vuetifyjs.com/images/cards/foster.jpg',
        title: 'Supermodel',
        artist: 'Foster the People'
      },
      {
        color: '#952175',
        src: 'https://cdn.vuetifyjs.com/images/cards/halcyon.png',
        title: 'Halcyon Days',
        artist: 'Ellie Goulding'
      }
    ]
  })
}
</script>

<style scoped>
.wrapper_main {
  display: grid;
  width: 100%;
  height: 100%;
  grid-gap: 15px;
  grid-template-areas:
    'h1 h1 h1'
    'logo h2 tel1'
    'logo h2 tel2'
    'logo text text';
  grid-template-rows: repeat(4, auto);
  grid-template-columns: repeat(3, 1fr);
  align-content: space-between;
  justify-content: center;
  align-items: center;
  justify-items: center;
  margin: auto;
  padding: 10% 15vmax 0;
  font-size: 20px;
}

.wrapper_main p {
  padding: 0;
}

.logo {
  grid-area: logo;
}

.logo img {
  width: 100%;
}

.h1 {
  grid-area: h1;
  font-size: 30px;
}

.h2 {
  grid-area: h2;
  font-size: 26px;
}

.tel1 {
  grid-area: tel1;
  justify-self: end;
}

.tel2 {
  grid-area: tel2;
  justify-self: end;
}

.tel1,
.tel2 {
  color: rgb(22, 94, 8);
}

.text {
  grid-area: text;
  font-size: 18px;
}

@media screen and (max-width: 1092px) {
  .wrapper_main {
    grid-template-areas:
      'h1 h1'
      '. h2'
      'logo tel1'
      'logo tel2'
      'logo text';
    grid-template-rows: auto 2fr 1fr 1fr auto;
    grid-template-columns: minmax(250px, 1fr) minmax(350px, 2fr);
    padding: 0 5vmax;
  }

  .h1 {
    font-size: 2.8vmax;
  }

  .h2 {
    font-size: 1.8vmax;
  }
}

@media screen and (max-width: 752px) {
  .wrapper_main {
    grid-template-areas:
      'h1 h1'
      'logo h2'
      'logo tel1'
      'logo tel2'
      'text text';
    grid-template-rows: auto 1fr 1fr 1fr auto;
    grid-template-columns: minmax(auto, 1fr) minmax(250px, 2fr);
    padding: 0 3vmax;
  }

  .h1 {
    font-size: 20px;
  }

  .h2 {
    font-size: 18px;
  }
}

@media screen and (max-width: 568px) {
  .wrapper_main {
    grid-template-areas:
      'h1'
      'h2'
      'logo'
      'tel1'
      'tel2'
      'text';
    grid-template-rows: repeat(6, auto);
    grid-template-columns: minmax(330px, 1fr);
    padding: 0 10px;
  }
}
</style>
