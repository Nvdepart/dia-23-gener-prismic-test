<template>
  <v-container>
    <v-row>
      <v-col>
        <h1>Home</h1>
        <div v-if="home">
          <v-img :src="home.data.image3.url"></v-img>
        </div>
        <pre>{{ home }}</pre>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      home: null,
    };
  },
  mounted() {
    let self = this;
    this.$prismic.api
      .getSingle("Home")
      .then((res) => {
        console.log("salut", res);
        self.home = res;
      })
      .catch((err) => {});
  },
};
</script>

<style lang="scss" scoped></style>
