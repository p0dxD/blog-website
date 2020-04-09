<template>
  <v-app dark>
    <v-app-bar :clipped-left="clipped" fixed app>
      <v-toolbar-title v-text="title" />
      <v-spacer />
      <v-switch v-model="$vuetify.theme.dark" hide-details inset label="Theme Dark"></v-switch>
      <v-divider
        class="mx-4"
        vertical
      ></v-divider>
      <nuxt-link v-if="$i18n.locale !== 'en'" :to="switchLocalePath('en')">English</nuxt-link>

      <nuxt-link v-if="$i18n.locale !== 'es'" :to="switchLocalePath('es')">Español</nuxt-link>
    </v-app-bar>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <v-footer :fixed="fixed" app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      fixed: false,
      clipped: false,
      title: "Jose Rodriguez"
    };
  }
};
</script>
