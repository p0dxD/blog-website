<template>
  <v-layout>
    <v-row>
        <div v-for="blog in blogs" :key="blog.name" :blog="blog">
            <v-row  justify="center">
            <Card :blog="blog" />
          </v-row>
          <div id="spacer"></div>
        </div>
    </v-row>
  </v-layout>
</template>

<script>
import Card from "~/components/Card";

export default {
  props: {
    blogs: {
      type: Array
    }
  },
  components: { Card }
};
</script>

<style >

#spacer {
  height: 30px;
  width: 100%;
}

</style>