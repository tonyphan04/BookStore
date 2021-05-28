<template>
  <div>
    <div id="app">
      <h1>Book Search</h1>
      <v-form>
        <v-container>
          <v-row>
            <v-col cols="12" sm="10">
              <v-text-field
                v-model="strStatus"
                solo
                label="Type"
                clearable
              ></v-text-field>
            </v-col>

            <v-col>
              <v-btn
                depressed
                color="teal lighten-1 "
                height="50"
                @click="add(strStatus)"
              >
                Submit
              </v-btn>
            </v-col>
          </v-row>
        </v-container>
      </v-form>
    </div>
    <!-- Data from API rendered -->
    <div>
      <v-expansion-panels popout>
        <v-expansion-panel v-for="m in msg.items" :key="m.id">
          <v-expansion-panel-header>
            {{ m.volumeInfo.title }}
          </v-expansion-panel-header>
          <v-expansion-panel-content>
            Author: {{ m.volumeInfo.authors }}
          </v-expansion-panel-content>
          <v-expansion-panel-content>
            Description: {{ m.volumeInfo.description }}
          </v-expansion-panel-content>
          <v-expansion-panel-content>
            Publisher: {{ m.volumeInfo.publisher }}
          </v-expansion-panel-content>
          <v-expansion-panel-content>
            Publish Date: {{ m.volumeInfo.publishDate }}
          </v-expansion-panel-content>
          <v-expansion-panel-content>
            Categories: {{ m.volumeInfo.categories }}
          </v-expansion-panel-content>
          <v-expansion-panel-content>
            Country: {{ m.saleInfo.country }}
          </v-expansion-panel-content>
        </v-expansion-panel>
      </v-expansion-panels>
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
}
</style>
<script>
export default {
  data: function () {
    return { err: "", msg: "", strStatus: "", dialog: false };
  },
  methods: {
    add: function (status) {
      //push status into statPosts array
      var self = this;
      var url = `https://www.googleapis.com/books/v1/volumes?q=""+intitle:${status}&key=AIzaSyC6v9MZRqMgf5KbQkwqQbBNsVN0W8ZwFpk`;

      fetch(url)
        .then((response) => {
          //turning the response into the usable data
          return response.json();
        })
        .then((data) => {
          //This is the data you wanted to get from url
          self.msg = data;
        })
        .catch((error) => {
          self.err = error;
        });
    },
  },
};
</script>
