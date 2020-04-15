<template>
  <v-card  max-width="80%" min-width="80%" class="mx-auto">
    <v-list-item>
      <v-list-item-avatar color="grey"></v-list-item-avatar>
      <v-list-item-content>
        <v-list-item-title class="headline"><h3>{{blog.title}}</h3></v-list-item-title>
        <v-list-item-subtitle>by {{blog.author}}</v-list-item-subtitle>
      </v-list-item-content>
    </v-list-item>
    <v-card-text><p>{{blog.description}}</p></v-card-text>
    <v-divider></v-divider>
    <v-card-text>Created: {{blog.date}}</v-card-text>
    <v-card-actions>
      <v-btn text color="deep-purple accent-4">
        <nuxt-link
          id="read-btn"
          :to="localePath({ name: 'blogs-slug', params: { slug: blog.name }})"
        class="date">{{$t('read_text')}}</nuxt-link>
      </v-btn>
      <v-spacer></v-spacer>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  props: {
    blog: {
      type: Object
    }
  }
};
</script>

<style scoped>
h3 { color: inherit; font-family: 'Lato', sans-serif; font-weight: 300; }


p { color: #adb7bd; font-family: 'Lucida Sans', Arial, sans-serif; font-size: 16px; line-height: 26px; text-indent: 30px; margin: 0; }



a:hover { color: #ffffff }


.date { background: #cad2d8; color: #ffffff; display: inline-block; font-family: 'Lato', sans-serif; font-size: 12px; font-weight: bold; line-height: 12px; letter-spacing: 1px; margin: 0 0 30px; padding: 10px 15px 8px; text-transform: uppercase; }
</style>