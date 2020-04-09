<template>
  <v-layout column justify-center align-center>
    <v-flex xs12 sm8 md6>
      <h1>{{ $t('posts_text') }}</h1>
      <BlogCard :blogs="blogs" />
    </v-flex>
  </v-layout>
</template>

<script>
import BlogCard from "~/components/BlogCard";

import blogsEn from "~/blogs/en/list.js";
import blogsEs from "~/blogs/es/list.js";

export default {
  layout: "main_page",
  components: { BlogCard },
  async asyncData({ app }) {
    const blogs = app.i18n.locale === "en" ? blogsEn : blogsEs;
    async function importAttributes(blogName) {
      const contentMd = await import(
        `~/blogs/${app.i18n.locale}/blog/${blogName}.md`
      );
      console.log("Attributes" + JSON.stringify(contentMd.attributes));
      return contentMd.attributes;
    }
    return Promise.all(blogs.map(blog => importAttributes(blog))).then(res => {
      return {
        blogs: res
      };
    });
  }
};
</script>
