<template>
  <v-app dark>
    <v-app-bar :clipped-left="clipped" fixed app>
      <a id="title" href="https://joserod.space">
        <v-toolbar-title v-text="title" />
      </a>
      <v-spacer />
      <v-switch v-model="$vuetify.theme.dark" hide-details inset></v-switch>
      <v-divider class="mx-4" vertical></v-divider>
      <nuxt-link v-if="$i18n.locale !== 'en'" :to="switchLocalePath('en')">En</nuxt-link>

      <nuxt-link v-if="$i18n.locale !== 'es'" :to="switchLocalePath('es')">Es</nuxt-link>
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
      title: "JR"
    };
  }
};
</script>

<style >
a {
  margin-right: 20px;
  font-size: 14px;
  color: #999;
  text-decoration: none;
  text-transform: uppercase;
  padding-top: 2px;
  padding-bottom: 2px;
  border-top: 1px solid transparent;
  border-bottom: 1px solid transparent;
  transition: color 0.25s;
  font-weight: 400;
  line-height: normal;
  cursor: pointer;
}
a:hover {
  color: #333;
}
#title,a.nuxt-link-active {
  color: #333;
  border-top: 1px solid #333;
  border-bottom: 1px solid #333;
  font-weight: 600;
}

.theme--dark.v-app-bar.v-toolbar.v-sheet {
    background-color: white;
}
</style>