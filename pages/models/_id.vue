<template>
  <article id="article#1" class="grand_block">
    <section class="grand_block__header">
      <h2 class="grand_block__header-item">РАКУШКА</h2>
      <h3 class="grand_block__header-item">Комната + Парная + Терраса</h3>
    </section>
    <section class="grand_block__main">
      <div class="grand_block__main-left">
        <!--img card-->
        <div id="img01" class="wrapper_img">
          <button class="noshow route" type="button" onclick="slide1()">
            ←
          </button>
          <button class="img-button" type="button">
            <img src="/images/rakushka/1 Ракушка 1.webp" alt="РАКУШКА" />
            <img
              src="/images/rakushka/2 Ракушка цех.webp"
              alt="Ракушка цех"
              class="noshow"
            />
            <img
              src="/images/rakushka/3 Ракушка 3.webp"
              alt="Ракушка"
              class="noshow"
            />
            <img
              src="/images/rakushka/4 Комната ракушка .webp"
              alt="Комната"
              class="noshow"
            />
            <img
              src="/images/rakushka/5 Ракушка комн .webp"
              alt="Комната с табуретом"
              class="noshow"
            />
            <img
              src="/images/rakushka/6 Ракушка комната печь стекл дверь.webp"
              alt="комната печь стекл дверь"
              class="noshow"
            />
            <img
              src="/images/rakushka/7 Парилка Ракушка.webp"
              alt="Парилка"
              class="noshow"
            />
            <img
              src="/images/rakushka/8 Печь в парилке.webp"
              alt="Парилка"
              class="noshow"
            />
            <img
              src="/images/rakushka/9 Ракушка доставка.webp"
              alt="доставка"
              class="noshow"
            />
          </button>
          <button class="noshow route" type="button" onclick="slide1('next')">
            →
          </button>
        </div>
        <div class="btn_wrap">
          <button class="btn_square" type="button">
            <span class="mdi mdi-camera"></span>
            фото
          </button>
          <button class="btn_square" type="button">
            <a
              title="Обзор бани РАКУШКА"
              type="video/mp4"
              href="/video/Ракушка обзор 2(0).mp4"
              onclick="yaCounter54743977.reachGoal('show_video'); return true;"
            >
              <span class="mdi mdi-play-circle btn_play"></span>
            </a>
            видео
          </button>
        </div>
        <div class="wrapper_price">
          <h3>Цена</h3>
          <section>
            <p>
              <span class="rank"><b>3</b> x 2,4 м</span> -
              <span class="rank">139 000 ₽</span>
            </p>
            <p>
              <span class="rank"><b>4</b> x 2,4 м</span> -
              <span class="rank">169 000 ₽</span>
            </p>
            <p>
              <span class="rank"><b>5</b> x 2,4 м</span> -
              <span class="rank">190 000 ₽</span>
            </p>
            <p>
              <span class="rank"><b>6</b> x 2,4 м</span> -
              <span class="rank">205 000 ₽</span>
            </p>
          </section>
        </div>
        <button class="btn" type="button">
          <a href="#article#1" onclick="jivo_api.open({start : 'call'});">
            Заказать звонок
          </a>
        </button>
      </div>
      <div class="grand_block__main-right">
        <h4>Материалы и комплектация</h4>
        <p>Терраса 1 метр с козырьком, пол: доска шип-паз, резные балясины.</p>
        <p>
          <b>Парная:</b> отделка вагонкой Липа Экстра, воздушный зазор,
          фольгированный утеплитель 8 мм, сухая обработанная доска 40 мм,
          мембрана от образования конденсата, имитация бруса, мягкая кровля.
          <br />Дверь липа. Пол доска 40 мм, герметичный слив, выведенный в
          трубу наружу, утеплитель 40мм. <br />Двухуровневый полок Липа Экстра,
          два декоративных светильника, окно, вентиляция.<br />Печь Термофор,
          бак 50 л, дымоход сэндвич.
        </p>
        <p>
          <b>Комната:</b> вагонка сосна сорт АB, воздушный зазор, фольгированный
          утеплитель 8 мм, сухая обработанная доска 40 мм, мембрана от
          образования конденсата, имитация бруса, мягкая кровля.<br />Стол, две
          скамьи сосна, вентиляция.<br />Дверь липа. Пол: утеплитель 40 мм,
          пароизоляция, доска половая 40 мм шип-паз.
        </p>
        <p>
          Скрытая проводка со светодиодными паронепроницаемыми светильниками в
          каждом отделении.
        </p>
        <p>
          <b>Основание:</b> обработанная огнебиозащитой доска 50*150, половые
          лаги, блоки для установки.
        </p>
        <button class="btn btn_additions">
          <a href="#additions">↓ Дополнительно можно заказать ↓</a>
        </button>
      </div>
    </section>
  </article>
</template>

<script>
export default {
  props: {}
}
</script>

<style lang="scss" scoped></style>
