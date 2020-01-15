<template>
  <v-app>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      :clipped-left="clipped"
      color="#CCA388"
      fixed
      elevate-on-scroll
      app
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-btn @click.stop="miniVariant = !miniVariant" icon>
        <v-icon>mdi-{{ `chevron-${miniVariant ? 'right' : 'left'}` }}</v-icon>
      </v-btn>
      <v-btn @click.stop="clipped = !clipped" icon>
        <v-icon>mdi-application</v-icon>
      </v-btn>
      <v-toolbar-title
        v-text="appTitle"
        class="font-weight-black secondary--text"
      />
      <v-spacer />
      <v-btn @click.stop="rightDrawer = !rightDrawer" icon>
        <v-icon>mdi-menu</v-icon>
      </v-btn>
    </v-app-bar>
    <v-content>
      <v-container fluid>
        <nuxt />
      </v-container>
    </v-content>
    <v-navigation-drawer v-model="rightDrawer" :right="right" temporary fixed>
      <v-list>
        <v-list-item @click.native="right = !right">
          <v-list-item-action>
            <v-icon light>
              mdi-repeat
            </v-icon>
          </v-list-item-action>
          <v-list-item-title>Switch drawer (click me)</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-footer absolute padless app color="accent">
      <v-card flat tile width="100%" class="accent text-center">
        <v-card-text class="pa-0 hidden-md-and-down">
          <v-btn
            v-for="({ title, to }, i) in items"
            :key="i"
            :to="to"
            color="white"
            nuxt
            exact
            text
            rounded
            class="my-2"
          >
            {{ title }}
          </v-btn>
        </v-card-text>
        <v-divider />
        <v-card-text class="pa-0">
          <span class="overline">
            Разработка сайта
            <a href="mailto:kachid76@gmail.com">М.Кахидзе</a>
          </span>
          <span>&copy; 2019</span>
        </v-card-text>
      </v-card>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: true,
      drawer: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Главная',
          to: '/'
        },
        {
          icon: 'mdi-home-circle',
          title: 'Модели',
          to: '/models'
        },
        {
          icon: 'mdi-wallet-plus',
          title: 'Преимущества',
          to: '/arrangement'
        },
        {
          icon: 'mdi-home-plus',
          title: 'Дополнительное оборудование',
          to: '/additions'
        },
        {
          icon: 'mdi-truck-delivery',
          title: 'Доставка и установка',
          to: '/delivery'
        },
        {
          icon: 'mdi-message-draw',
          title: 'Отзывы',
          to: '/reviews'
        },
        {
          icon: 'mdi-map-marker',
          title: 'Контакты',
          to: '/contacts'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      appTitle: 'SRUBOFF'
    }
  }
}
</script>
