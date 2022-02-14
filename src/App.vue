<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <v-toolbar-title>ĐẦU TƯ 101</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        v-for="link in links"
        :key="`${link.label}-header-link`"
        text
        rounded
        :to="link.url"
      >
        {{ link.label }}
      </v-btn>
      <v-btn @click="toggleTheme" text rounded>
        Chủ đề
      </v-btn>
    </v-app-bar>
    <v-content>
      <router-view></router-view>
    </v-content>
    <v-footer color="primary lighten-1" padless>
      <v-layout justify-center wrap>
        <v-btn
          v-for="link in links"
          :key="`${link.label}-footer-link`"
          color="white"
          text
          rounded
          class="my-2"
          :to="link.url"
        >
          {{ link.label }}
        </v-btn>
        <v-flex primary lighten-2 py-4 text-center white--text xs12>
          {{ new Date().getFullYear() }} — <strong>DAU TU 101 All Right Reserved.</strong>
        </v-flex>
      </v-layout>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      links: [
        {
          label: 'Trang chủ',
          url: '/'
        },
        {
          label: 'Bảng giá',
          url: '/dashboard'
        },
        {
          label: 'Trung tâm phân tích',
          url: '/dashboard'
        },
        {
          label: 'Đăng nhập',
          url: '/login'
        },
        {
          label: 'Đăng ký',
          url: '/signup'
        }

      ]
    }
  },
  methods: {
    toggleTheme() {
      this.$vuetify.theme.themes.dark.anchor = '#41B883'
      this.$vuetify.theme.dark = !this.$vuetify.theme.dark
    }
  }
}
</script>
