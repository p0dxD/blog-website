<template>
  <v-layout>
    <v-row>
      <v-flex class="text-center">
        <v-col cols="12" md="12" xs="12">
          <v-card class="d-flex align-content-start flex-wrap mx-auto">
            <v-card-text>
                              <v-btn
                  outlined
                  class="align-content-center text--primary"
                >              <nuxt-link
                id="read-btn"
                :to="localePath({ name: 'blogs-slug', params: { slug: blog.name }})"
              >{{blog.title}}</nuxt-link></v-btn>
              <p>About article:</p>
              <div class="text--primary">{{blog.description}}</div>
              <br />
              <p>Last updated: {{blog.updated}}</p>
              <p>Date created: {{blog.date}}</p>
            </v-card-text>
          </v-card>
        </v-col>
      </v-flex>
    </v-row>
  </v-layout>
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
.md-card.md-with-hover {
  height: 98%;
  right: -3px;
}
#container-project {
  position: relative;
}


.titles {
  color: #7c795d;
  font-family: "Trocchi", serif;
  font-size: 45px;
  font-weight: normal;
  line-height: 48px;
  margin: 0;
  padding: 25px;
}
.subtitles {
  color: #7c795d;
  font-family: "Source Sans Pro", sans-serif;
  font-size: 15px;
  font-weight: 400;
  line-height: 32px;
}

.md-card .md-subhead {
  padding-bottom: 15px;
}

.vertical-center {
  margin: 0;
  position: absolute;
  top: 50%;
  -ms-transform: translateY(-50%);
  transform: translateY(-50%);
}

a#read-btn {
    color: inherit;
}
</style>