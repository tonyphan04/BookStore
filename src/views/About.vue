<template>
  <div>
    <div id="app">
      <h1>About me</h1>
      <p>
        Stop acting as if life is a rehearsal. Live this day as if it were your
        last. The past is over and gone. The future is not guaranteed.
      </p>

      <v-row>
        <v-col cols="6" sm="4"> </v-col>

        <v-col cols="6" sm="4">
          <v-img
            lazy-src="https://picsum.photos/id/11/10/6"
            max-height="500"
            max-width="500"
            src="https://picsum.photos/id/11/500/300"
          ></v-img>
        </v-col>
      </v-row>
      <v-divider vertical></v-divider>
      <div class="para">
        <p>
          Phasellus feugiat arcu sapien, et iaculis ipsum elementum sit amet.
          Mauris cursus commodo interdum. Praesent ut risus eget metus luctus
          accumsan id ultrices nunc. Sed at orci sed massa consectetur dignissim
          a sit amet dui. Duis commodo vitae velit et faucibus. Morbi vehicula
          lacinia malesuada. Nulla placerat augue vel ipsum ultrices, cursus
          iaculis dui sollicitudin. Vestibulum eu ipsum vel diam elementum
          tempor vel ut orci. Orci varius natoque penatibus et magnis dis
          parturient montes, nascetur ridiculus mus
        </p>
        <p>
          Phasellus feugiat arcu sapien, et iaculis ipsum elementum sit amet.
          Mauris cursus commodo interdum. Praesent ut risus eget metus luctus
          accumsan id ultrices nunc. Sed at orci sed massa consectetur dignissim
          a sit amet dui. Duis commodo vitae velit et faucibus. Morbi vehicula
          lacinia malesuada. Nulla placerat augue vel ipsum ultrices, cursus
          iaculis dui sollicitudin. Vestibulum eu ipsum vel diam elementum
          tempor vel ut orci. Orci varius natoque penatibus et magnis dis
          parturient montes, nascetur ridiculus mus
        </p>
      </div>
      <v-btn
        v-for="list in lists"
        :key="list.id"
        :href="list.links"
        class="mx-4"
        icon
      >
        <v-icon size="24px">
          {{ list.icons }}
        </v-icon>
      </v-btn>
    </div>
  </div>
</template>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  padding: 50px;
}
div.para {
  width: 1000px;
  margin: 0 auto;
  margin-top: 0px;
  padding-left: 50px;
  padding-right: 100px;
}
</style>
<script>
export default {
  data() {
    return {
      lists: [
        { id: 1, icons: "mdi-facebook", links: "https://www.facebook.com/" },
        { id: 2, icons: "mdi-twitter", links: "https://twitter.com/?lang=vi" },
        {
          id: 3,
          icons: "mdi-linkedin",
          links: "https://www.linkedin.com/feed/",
        },
        {
          id: 4,
          icons: "mdi-instagram",
          links: "https://www.instagram.com/?hl=vi",
        },
      ],
    };
  },
};
</script>