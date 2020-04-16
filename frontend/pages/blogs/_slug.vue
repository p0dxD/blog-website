<template>
  <v-layout column justify-center align-center>
    <v-flex xs12 sm8 md6>
      <nuxt-link :to="localePath('index')">back</nuxt-link>
      <client-only>
        <DynamicMarkdown :render-func="renderFunc" :static-render-funcs="staticRenderFuncs" />
        <vue-disqus v-if="true" shortname="vue-blog-demo"
          :key="pageName" :identifier="pageName" :url="`https://joserod.space:81/blogs/${pageName}`"/>
      </client-only>
    </v-flex>
  </v-layout>
</template>

<script>
import DynamicMarkdown from "~/components/DynamicMarkdown.vue";
export default {
  layout: "main_page",
  async asyncData({ params, app }) {
    const contentMd = await import(
      `~/blogs/${app.i18n.locale}/blog/${params.slug}.md`
    );
    console.log("Here" + JSON.stringify(contentMd));
    return {
      pageName: params.slug,
      renderFunc: `(${contentMd.vue.render})`,
      staticRenderFuncs: `[${contentMd.vue.staticRenderFns}]`
    };
  },
  components: { DynamicMarkdown },
};
</script>