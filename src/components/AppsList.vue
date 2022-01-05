<template>
  <v-card class="mx-auto">
    <!-- <v-app-bar
    >
      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-toolbar-title>Indus App Bazaar</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>
    </v-app-bar> -->

    <v-container class="elevation-0">
      <v-row dense>
        <v-col cols="12">
          <v-card class="elevation-0">
            <v-card-title style="padding-left: 0px; padding-right: 0px">
              <v-chip
                class="ma-2 app-chip"
                color="orange"
                label
                dark
                style="background-image: linear-gradient(to right, orange, red)"
              >
                Here only
              </v-chip>
              Exclusive On App Bazaar
              <v-spacer></v-spacer>
              <v-btn icon>
                <v-icon>mdi-arrow-right</v-icon>
              </v-btn>
            </v-card-title>
            <v-card-actions>
              <v-row style="flex-wrap: nowrap; overflow-x: auto">
                <v-card
                  v-for="(item, index) in exclusiveApps"
                  :key="index"
                  class="mx-auto elevation-0 px-1"
                  max-width="80"
                  @click="redirectToAppDetails"
                >
                  <v-img :src="item.src" width="72" height="72"></v-img>

                  <v-card-title
                    v-text="item.title"
                    class="text-truncate apps-title"
                    text-center
                    wrap
                  ></v-card-title>
                  <div class="apps-subtitle">
                    <span class="text-center mx-5"> {{ item.size }}</span>
                  </div>
                  <v-card-actions>
                    <v-btn
                      height="28px"
                      depressed
                      width="100%"
                      @click="download = true"
                    >
                      <v-icon>mdi-download</v-icon>
                    </v-btn>
                  </v-card-actions>
                </v-card>
              </v-row>
            </v-card-actions>
          </v-card>
        </v-col>

        <v-col cols="12">
          <v-card class="elevation-0 social-card">
            <v-card-title style="padding-left: 0px; font-size: 1rem !important">
              Your Friends Choice
              <v-spacer></v-spacer>
              <span style="font-size: 0.8rem !important; opacity: 0.7"
                >More</span
              >
            </v-card-title>
            <div class="text-subtitle-1 pt-2 pb-3">
              <v-img
                width="230"
                :src="require('../assets/images/frnds.png')"
              ></v-img>
            </div>
            <v-card-actions>
              <v-row style="flex-wrap: nowrap; overflow-x: auto">
                <v-card
                  v-for="(item, index) in friendsChoice"
                  :key="index"
                  class="mx-auto elevation-0 px-2 social-card-apps"
                  width="120"
                >
                  <v-img
                    :src="item.src"
                    width="80"
                    height="80"
                    style="display: block; margin: auto; margin-top: 10px"
                  ></v-img>

                  <v-card-title
                    v-text="item.title"
                    class="justify-center text-truncate apps-title width-100"
                    text-center
                    wrap
                  ></v-card-title>
                  <div class="apps-subtitle width-100">
                    <v-rating
                      :value="1"
                      color="amber"
                      dense
                      readonly
                      size="14"
                      length="1"
                      style="display: inline-block"
                    ></v-rating>
                    <span style="color: #ffb74d"> 4.2 </span> |
                    <span class="text-center"> {{ item.size }}</span
                    ><v-icon class="ml-5" small>mdi-download</v-icon>
                  </div>
                </v-card>
              </v-row>
            </v-card-actions>
          </v-card>
        </v-col>

        <v-col cols="12" class="pt-4">
          <v-card
            class="elevation-0"
            style="background-color: aliceblue; border-radius: 15px"
          >
            <v-card-title>
              Apps Around You
              <v-spacer></v-spacer>
              <v-btn icon>
                <v-icon>mdi-map</v-icon>
              </v-btn>
            </v-card-title>
            <v-card-actions>
              <v-img
                style="border-radius: 15px"
                :src="require('../assets/images/geo.png')"
              ></v-img>
            </v-card-actions>
            <v-card-actions>
              <v-col cols="12">
                <v-row
                  v-for="(item, index) in geoLocationApps"
                  :key="index"
                  class="pb-4"
                >
                  <v-col
                    cols="4"
                    class="text-right pa-0"
                    @click="openDialog(index)"
                  >
                    <v-img
                      :src="item.src"
                      width="72"
                      height="72"
                      class="xcols-img"
                    ></v-img>
                  </v-col>
                  <v-col cols="6" class="text-left pa-0">
                    <div class="text-subtitle-2 text-truncate">
                      {{ item.title }}
                    </div>
                    <div class="text-caption">{{ item.dev }}</div>
                    <div class="apps-subtitle">
                      <v-rating
                        :value="1"
                        color="amber"
                        dense
                        readonly
                        size="14"
                        length="1"
                        style="display: inline-block"
                      ></v-rating>
                      <span style="color: #ffb74d"> {{ item.rating }}</span> |
                      <span class="text-center"> {{ item.size }}</span>
                    </div>
                  </v-col>
                  <v-col cols="2" class="text-right pa-0">
                    <v-btn icon class="mt-5" @click="download = true">
                      <v-icon>mdi-download</v-icon>
                    </v-btn>
                  </v-col>
                </v-row>
              </v-col>
            </v-card-actions>
          </v-card>
        </v-col>

        <v-col cols="12">
          <v-card class="elevation-0">
            <v-card-title>
              Christmas Special
              <v-spacer></v-spacer>
              <v-btn icon>
                <v-icon>mdi-arrow-right</v-icon>
              </v-btn>
            </v-card-title>
            <v-card-actions>
              <v-row style="flex-wrap: nowrap; overflow-x: auto">
                <v-card
                  v-for="(item, index) in christmasSpecial"
                  :key="index"
                  class="mx-auto elevation-0 px-2"
                  max-width="170"
                  @click="redirectToAppDetails"
                >
                  <v-img :src="item.src"></v-img>
                </v-card>
              </v-row>
            </v-card-actions>
          </v-card>
        </v-col>

        <v-col cols="12">
          <v-card class="elevation-0">
            <v-card-title>
              Editor's Choice Apps
              <v-spacer></v-spacer>
              <v-btn icon>
                <v-icon>mdi-arrow-right</v-icon>
              </v-btn>
            </v-card-title>
            <v-card-actions>
              <v-row style="flex-wrap: nowrap; overflow-x: auto">
                <v-card
                  v-for="(item, index) in editorsChoice"
                  :key="index"
                  class="mx-auto elevation-0 px-1"
                  max-width="80"
                  @click="redirectToAppDetails"
                >
                  <v-img :src="item.src" width="72" height="72"></v-img>

                  <v-card-title
                    v-text="item.title"
                    class="text-truncate apps-title"
                    text-center
                    wrap
                  ></v-card-title>
                  <div class="apps-subtitle">
                    <v-rating
                      :value="1"
                      color="amber"
                      dense
                      readonly
                      size="14"
                      length="1"
                      style="display: inline-block"
                    ></v-rating>
                    <span style="color: #ffb74d"> {{ item.rating }}</span> |
                    <span class="text-center"> {{ item.size }}</span>
                  </div>
                  <v-card-actions>
                    <v-btn
                      height="28px"
                      depressed
                      width="100%"
                      @click="download = true"
                    >
                      <v-icon>mdi-download</v-icon>
                    </v-btn>
                  </v-card-actions>
                </v-card>
              </v-row>
            </v-card-actions>
          </v-card>
        </v-col>
        <v-col cols="auto">
          <v-dialog
            transition="dialog-bottom-transition"
            max-width="600"
            v-model="showDialog0"
          >
            <v-card>
              <v-toolbar>Flipkart Online Shopping</v-toolbar>
              <v-card-text class="pt-4">
                <v-img
                  :src="require('../assets/geolocation/flipkar_offer.jpg')"
                ></v-img>
              </v-card-text>
              <v-card-actions class="justify-end">
                <v-btn class="pa-2" color="success" text
                  >Install<v-icon right dark> mdi-download </v-icon></v-btn
                >
                <v-btn text @click="showDialog0 = false">Close</v-btn>
              </v-card-actions>
            </v-card>
          </v-dialog>
        </v-col>
        <v-col cols="auto">
          <v-dialog
            transition="dialog-bottom-transition"
            max-width="600"
            v-model="showDialog1"
          >
            <v-card>
              <v-toolbar>Airtel Thanks - Recharge Now</v-toolbar>
              <v-card-text class="pt-4">
                <v-img
                  :src="require('../assets/geolocation/airtel_offer.jpg')"
                ></v-img>
              </v-card-text>
              <v-card-actions class="justify-end">
                <v-btn class="pa-2" text color="success"
                  >Install<v-icon right dark> mdi-download </v-icon></v-btn
                >
                <v-btn text @click="showDialog1 = false">Close</v-btn>
              </v-card-actions>
            </v-card>
          </v-dialog>
        </v-col>

        <v-col cols="auto">
          <v-dialog
            transition="dialog-bottom-transition"
            max-width="600"
            v-model="showDialog2"
          >
            <v-card>
              <v-toolbar>Duolingo: Learn English</v-toolbar>
              <v-card-text class="pt-4">
                <v-img
                  :src="require('../assets/geolocation/duolingo_offer.jpeg')"
                ></v-img>
              </v-card-text>
              <v-card-actions class="justify-end">
                <v-btn class="pa-2" text color="success"
                  >Install<v-icon right dark> mdi-download </v-icon></v-btn
                >
                <v-btn text @click="showDialog2 = false">Close</v-btn>
              </v-card-actions>
            </v-card>
          </v-dialog>
        </v-col>
        <v-dialog v-model="download" hide-overlay persistent width="300">
          <v-card color="primary" dark>
            <v-card-text>
              Please wait while we dwnload the App
              <v-progress-linear
                indeterminate
                color="white"
                class="mb-0"
              ></v-progress-linear>
            </v-card-text>
          </v-card>
        </v-dialog>
      </v-row>
    </v-container>
  </v-card>
</template>
<script>
export default {
  methods: {
    redirectToAppDetails() {
      window.location.href = "https://competent-thompson-a145d8.netlify.app/";
    },
    openDialog(index) {
      if (index == 0) this.showDialog0 = true;
      else if (index == 1) this.showDialog1 = true;
      else if (index == 2) this.showDialog2 = true;
    },
  },
  watch: {
      download (val) {
        if (!val) return

        setTimeout(() => (this.download = false), 3000)
      },
    },
  data: () => ({
    showDialog0: false,
    showDialog1: false,
    showDialog2: false,
    download: false,
    exclusiveApps: [
      {
        src: require("../assets/images/sixth.jpg"),
        title: "Teen Patti",
        size: "8 MB",
      },
      {
        src: require("../assets/images/seventh.jpg"),
        title: "Spin and Win",
        size: "9 MB",
      },
      {
        src: require("../assets/images/eigth.jpg"),
        title: "Kashkick",
        size: "14 MB",
      },
      {
        src: require("../assets/images/ninth.jpg"),
        title: "My Team 11",
        size: "9 MB",
      },
      {
        src: require("../assets/images/tenth.jpg"),
        title: "Make Mytrip",
        size: "8 MB",
        rating: 4.2,
      },
      {
        src: require("../assets/images/eleventh.jpg"),
        title: "Akash Institute",
        size: "9 MB",
        rating: 4.2,
      },
    ],
    christmasSpecial: [
      {
        src: require("../assets/images/first.png"),
        title: "Teen Patti",
        size: "8 MB",
      },
      {
        src: require("../assets/images/second.png"),
        title: "Team 11",
        size: "9 MB",
      },
      {
        src: require("../assets/images/third.png"),
        title: "Kashkick",
        size: "14 MB",
      },
    ],
    editorsChoice: [
      {
        src: require("../assets/images/phonepe.png"),
        title: "PhonePe",
        size: "8 MB",
        rating: 4.2,
      },
      {
        src: require("../assets/images/eleventh.jpg"),
        title: "Akash Institute",
        size: "9 MB",
        rating: 4.2,
      },
      {
        src: require("../assets/images/twelvth.jpg"),
        title: "Farmiso",
        size: "14 MB",
        rating: 4.2,
      },
      {
        src: require("../assets/images/thirtheenth.jpg"),
        title: "Olx: Buy & Sell",
        size: "14 MB",
        rating: 4.2,
      },
    ],
    friendsChoice: [
      {
        src: require("../assets/images/fourth.png"),
        title: "Candy Crush Saga",
        size: "18 MB",
      },
      {
        src: require("../assets/images/fifth.png"),
        title: "Amazon music",
        size: "18 MB",
      },
      {
        src: require("../assets/images/sixth.jpg"),
        title: "Teen Patti",
        size: "8 MB",
      },
      {
        src: require("../assets/images/seventh.jpg"),
        title: "Team 11",
        size: "9 MB",
      },
    ],
    geoLocationApps: [
      {
        src: require("../assets/geolocation/flipkart.jpg"),
        title: "Flipkart Online Shopping",
        size: "18 MB",
        rating: 4.6,
        offer: require("../assets/geolocation/flipkart.jpg"),
        dev: "Flipkart",
      },
      {
        src: require("../assets/geolocation/airtel.png"),
        title: "Airtel Thanks - Recharge Now",
        size: "18 MB",
        rating: 3.9,
        offer: require("../assets/geolocation/flipkart.jpg"),
        dev: "Airtel",
      },
      {
        src: require("../assets/geolocation/duolingo.png"),
        title: "Duolingo: Learn English",
        size: "8 MB",
        rating: 3.5,
        offer: require("../assets/geolocation/flipkart.jpg"),
        dev: "XOKind",
      },
    ],
  }),
};
</script>
<style scoped>
.v-card__title {
  font-size: 1.1rem !important;
  line-height: 1rem !important;
  padding-bottom: 0 !important;
}
.apps-title {
  font-size: 0.8rem !important;
  padding: 3px 16px 0px 5px !important;
  display: inline-block !important;
  width: 78px;
}
.apps-subtitle {
  font-size: 0.6rem !important;
  color: #252525bf;
}
.v-chip.v-chip--label {
  border-radius: 6px !important;
}
.social-card {
  background-image: linear-gradient(120deg, #ffc85b 10%, #e3830b 70%);
  padding: 5px 18px;
  border-radius: 18px !important;
}
.social-card-apps {
  border-radius: 15px !important;
  padding: 8px;
}
.social-card-apps.v-card.v-sheet {
  margin-right: 10px !important;
}
.app-chip {
  height: 24px !important;
  font-size: 11px !important;
}
.v-card__actions .v-btn.v-btn {
  padding: 0 !important;
  margin-left: -4px !important;
  min-width: 68px !important;
  border-radius: 7px !important;
}
.width-100 {
  width: 110px !important;
}
.xcols-img {
  border-radius: 18px !important;
  display: block;
  margin: auto;
}
</style>