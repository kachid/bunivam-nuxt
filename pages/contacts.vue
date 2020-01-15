<template>
  <v-row justify="center" align="center">
    <v-col cols="12" lg="9">
      <v-card>
        <v-card-title>КОНТАКТЫ</v-card-title>
        <v-card-subtitle>
          <a href="tel:+73433833450">Телефон: 8 (343) 383-34-50</a><br /><br />
          <a href="tel:+79221468521">WhatsApp: +7 (922) 146-85-21</a>
        </v-card-subtitle>
        <v-card-text>
          <div>Выставочные образцы наших бань можно посмотреть по адресу:</div>
          <address>Екатеринбург, Металлургов 70</address>
        </v-card-text>
        <v-img src="/images/Выставка_1.jpg" alt="Баня на выставке" />
        <v-card-text>
          <div>
            Площадка между Новомосковским рынком и Леруа Мерлен. Ориентир киоск
            Шаурма
          </div>
          <br />
          <div id="map" class="map">
            <script
              type="text/javascript"
              charset="utf-8"
              async
              src="https://api-maps.yandex.ru/services/constructor/1.0/js/?um=constructor%3Ae61f596856951c1af8c16c32d2f1f0f243b31285954c3708cf483511e52dbcc2&amp;width=100%25&amp;height=400&amp;lang=ru_RU&amp;scroll=true"
            ></script>
          </div>
          <div>Производство: г. Заречный</div>
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>
