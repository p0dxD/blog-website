<template>
  <v-layout column justify-center align-center>
    <v-flex xs12 sm8 md6>
      <nuxt-link :to="localePath('index')">back</nuxt-link>
      <h1>{{ $t('greeting') }}</h1>
       <component :is="renderFunc" />
    </v-flex>
  </v-layout>
</template>

<script>
export default {
  layout: "main_page",
  async asyncData({params, app}) {
     const contentMd = await import(`~/blogs/${app.i18n.locale}/blog/${params.slug}.md`)
      return {
        renderFunc: contentMd.vue.component
      };
  }
};
</script>