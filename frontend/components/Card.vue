<template>
  <v-card width="350" class="mx-auto">
    <v-list-item>
      <v-list-item-avatar color="grey"></v-list-item-avatar>
      <v-list-item-content>
        <v-list-item-title class="headline">{{blog.title}}</v-list-item-title>
        <v-list-item-subtitle>by {{blog.author}}</v-list-item-subtitle>
      </v-list-item-content>
    </v-list-item>
    <v-img src="https://cdn.vuetifyjs.com/images/cards/mountain.jpg" height="194"></v-img>

    <v-card-text>{{blog.description}}</v-card-text>
    <v-divider></v-divider>
    <v-card-text>{{blog.date}}</v-card-text>
    <v-card-actions>
      <v-btn text color="deep-purple accent-4">
        <nuxt-link
          id="read-btn"
          :to="localePath({ name: 'blogs-slug', params: { slug: blog.name }})"
        >{{$t('read_text')}}</nuxt-link>
      </v-btn>
      <v-spacer></v-spacer>
      <v-btn icon>
        <v-icon>mdi-heart</v-icon>
      </v-btn>
      <v-btn icon>
        <v-icon>mdi-share-variant</v-icon>
      </v-btn>
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