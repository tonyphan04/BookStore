<template>
  <div>
    <v-container>
      <!-- Creating carousel  -->
      <div class="carousel">
        <v-carousel :show-arrows="true">
          <v-carousel-item
            v-for="(item, i) in items"
            :key="i"
            :src="item.src"
          ></v-carousel-item>
        </v-carousel>
      </div>
      <!-- List of best seller books -->
      <div class="block-title">
        <h2>Best seller</h2>
      </div>
      <!-- Divide list into 3 columns -->
      <v-row no-gutters>
        <v-col cols="12" xs="4" sm="4" lg="4">
          <v-card :loading="loading" class="mx-auto my-12" max-width="374">
            <template slot="progress">
              <v-progress-linear
                color="deep-purple"
                height="10"
                indeterminate
              ></v-progress-linear>
            </template>

            <v-img height="500" src="theRevolution.jpg"></v-img>

            <v-card-title>The Revolution</v-card-title>

            <v-card-text>
              <v-row align="center">
                <v-rating
                  :value="4.5"
                  color="amber"
                  dense
                  half-increments
                  readonly
                  size="14"
                ></v-rating>
                <div class="grey--text">19$</div>
              </v-row>

              <div class="my-4 subtitle-1">Amazon AU</div>
            </v-card-text>
          </v-card>
        </v-col>
        <v-col cols="12" xs="4" sm="4" lg="4">
          <v-card :loading="loading" class="mx-auto my-12" max-width="374">
            <template slot="progress">
              <v-progress-linear
                color="deep-purple"
                height="10"
                indeterminate
              ></v-progress-linear>
            </template>

            <v-img height="500" src="book2.jpg"></v-img>

            <v-card-title>The Intelligent Investor</v-card-title>

            <v-card-text>
              <v-row align="center">
                <v-rating
                  :value="4.5"
                  color="amber"
                  dense
                  half-increments
                  readonly
                  size="14"
                ></v-rating>
                <div class="grey--text">60$</div>
              </v-row>

              <div class="my-4 subtitle-1">Amazon AU</div>
            </v-card-text>
          </v-card>
        </v-col>
        <v-col cols="12" xs="4" sm="4" lg="4">
          <v-card :loading="loading" class="mx-auto my-12" max-width="374">
            <template slot="progress">
              <v-progress-linear
                color="deep-purple"
                height="10"
                indeterminate
              ></v-progress-linear>
            </template>

            <v-img height="500" src="book3.png"></v-img>

            <v-card-title>A Brief History of Humankind</v-card-title>

            <v-card-text>
              <v-row align="center">
                <v-rating
                  :value="4.5"
                  color="amber"
                  dense
                  half-increments
                  readonly
                  size="14"
                ></v-rating>
                <div class="grey--text">36$</div>
              </v-row>

              <div class="my-4 subtitle-1">Amazon AU</div>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
      <!-- Advertisement card -->
      <v-container fluid>
        <v-row dense>
          <v-col v-for="card in cards" :key="card.title" :cols="card.flex">
            <v-hover v-slot="{ hover }">
              <v-card class="text-center">
                <div id="block-advertisement-card">
                  <v-card-text v-text="card.title"></v-card-text>
                  <v-expand-transition>
                    <div
                      v-if="hover"
                      class="transition-fast-in-fast-out text-center"
                      style="height: 100%"
                    >
                      <span>
                        <v-card-text v-text="card.text"></v-card-text
                      ></span>
                    </div>
                  </v-expand-transition>
                </div>

                <!-- </v-img> -->
              </v-card>
            </v-hover>
          </v-col>
        </v-row>
      </v-container>
    </v-container>
    <!-- Footer -->
    <v-footer dark padless>
      <v-card class="teal lighten-1 white--text flex">
        <v-card-text class="white--text pt-0">
          <v-row>
            <v-col sm="3" xs="3" lg="3">
              Shopping guide
              <ul>
                <li><p>Blog</p></li>
                <li><p>FAQ</p></li>
                <li><p>Payment</p></li>
                <li><p>Shipment</p></li>
              </ul>
            </v-col>
            <v-col sm="3" xs="3" lg="3">
              Style advisor
              <ul>
                <li><p>Your account</p></li>
                <li><p>Information</p></li>
                <li><p>Address</p></li>
                <li><p>Discount</p></li>
              </ul>
            </v-col>

            <v-col sm="3" xs="3" lg="3">
              Informmation
              <ul>
                <li><p>Site Map</p></li>
                <li><p>Search Terms</p></li>
                <li><p>Advanced Search</p></li>
                <li><p>About Us</p></li>
              </ul>
            </v-col>
            <v-col sm="3" xs="3" lg="3">
              Contact Us
              <ul>
                <li><p>Swinburne University of Technology</p></li>
                <li><p>0123456789</p></li>
                <li><p>102889939@swinburne.edu.au</p></li>
              </ul>
            </v-col>
          </v-row>
        </v-card-text>
        <v-divider></v-divider>
        <v-card-title class="teal lighten-1">
          <strong class="subheading"
            >Get connected with us on social networks!</strong
          >

          <v-spacer></v-spacer>

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
        </v-card-title>
      </v-card>
    </v-footer>
  </div>
</template>
<style>
.block-title {
  color: #333;
}
.carousel {
  position: relative;
  width: 1300px;
}
#block-advertisement-card {
  color: #333;
  display: block;
  font-size: 22px;
  line-height: 28px;
  text-align: center;
  margin-bottom: 15px;
  text-transform: uppercase;
  font-family: "proximanova", "Helvetica", Arial sans-serif;
}
span {
  color: #0ab3a3;
}
</style>
<script>
export default {
  data() {
    return {
      items: [
        {
          src: "banner1.jpg",
        },
        {
          src: "banner2.png",
        },
        {
          src: "banner3.png",
        },
        {
          src: "banner4.jpg",
        },
      ],
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
      cards: [
        {
          title: "Free delivery",
          text: "Discount 50%",
          src: "https://cdn.vuetifyjs.com/images/cards/house.jpg",
          flex: 3,
        },
        {
          title: "Photography books",
          text: "Featured",
          src: "https://cdn.vuetifyjs.com/images/cards/road.jpg",
          flex: 3,
        },
        {
          title: "Keep reading",
          text: "Reading is the best for giving idea",
          src: "https://cdn.vuetifyjs.com/images/cards/plane.jpg",
          flex: 3,
        },
        {
          title: "New books",
          text: "Sales 70%",
          src: "https://cdn.vuetifyjs.com/images/cards/plane.jpg",
          flex: 3,
        },
      ],
    };
  },
};
</script>
