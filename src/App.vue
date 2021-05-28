<template>
  <v-app id="inspire">
    <v-app-bar class="teal lighten-1" flat tile app>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-app-bar-title>BookLib </v-app-bar-title>
    </v-app-bar>
    <v-navigation-drawer v-model="drawer" dark app>
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="title"> Categories </v-list-item-title>
        </v-list-item-content>
      </v-list-item>

      <v-list dense nav>
        <v-list-item-group v-model="selectedItem">
          <v-list-item
            v-for="item in items"
            :key="item.title"
            :to="item.to"
            link
          >
            <v-list-item-icon>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-item-icon>

            <v-list-item-content>
              <v-list-item-title>{{ item.title }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
          <v-divider></v-divider>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
    <v-main>
      <router-view></router-view>
    </v-main>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    drawer: null,
    selectedItem: 1,
    items: [
      { title: "Home", icon: "mdi-view-dashboard", to: "/" },
      { title: "Search book by name", icon: "mdi-image", to: "/titleSearch" },
      {
        title: "Search book by author",
        icon: "mdi-image",
        to: "/authorSearch",
      },
      { title: "Register", icon: "mdi-image", to: "/register" },
      { title: "About me", icon: "mdi-image", to: "/about" },
    ],

    overlay: false,
    zIndex: 0,
  }),
};
</script>