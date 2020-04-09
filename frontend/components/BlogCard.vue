<template>
  <v-app id="inspire">
    <v-container>
      <v-row  justify="center">
        <div v-for="blog in blogs" :key="blog.name" :blog="blog">
          <v-col cols="12">
            <Card :blog="blog" />
          </v-col>
        </div>
      </v-row>
    </v-container>
  </v-app>
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
#read-btn {
  color: #6200ea;
}

#read-btn:link {
  text-decoration: none;
  color: #6200ea;
}

#read-btn:visited {
  text-decoration: none;
  color: #6200ea;
}

#read-btn:hover {
  text-decoration: none;
  color: blue;
}

#read-btn:active {
  text-decoration: none;
  color: #6200ea;
}
</style>