<template>
  <v-card
    class="mx-auto"
  >
    <v-app-bar
    >
      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-toolbar-title>Indus App Bazaar</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>
    </v-app-bar>

    <v-container class="elevation-0">
      <v-row dense>
        <v-col cols="12">
          <v-card class="elevation-0"
          >
            <v-card-title>
              <v-chip
      v-if="chip4"
      class="ma-2"
      close
      color="orange"
      label
    >
      Here only
    </v-chip> Exclusive On App Bazaar
              <v-spacer></v-spacer>
                    <v-btn icon>
                    <v-icon>mdi-arrow-right</v-icon>
                </v-btn>
            </v-card-title>
            <v-card-actions>
                <v-row style="flex-wrap: nowrap;overflow-x: auto;">
                    <v-card v-for="(item, index) in exclusiveApps" :key="index" class="mx-auto elevation-0 px-2"
    max-width="120">

    <v-img
      :src="item.src"
     width="104"
      height="104" 
    ></v-img>

    <v-card-title v-text="item.title" class="justify-center text-truncate apps-title" text-center
      wrap></v-card-title>
    <v-card-subtitle class="apps-subtitle"><span class="text-center mx-7"> {{ item.size }}</span></v-card-subtitle>
    <v-card-actions>
        <v-btn
        height="28px"
        depressed
        width="100%"
        >
        <v-icon>mdi-download</v-icon>
        </v-btn>
    </v-card-actions>


                    </v-card>
                </v-row>
            </v-card-actions>
          </v-card>
        </v-col>

        <!-- <v-col
          v-for="(item, i) in items"
          :key="i"
          cols="12"
        >
          <v-card
            dark
          >
            <div class="d-flex flex-no-wrap justify-space-between">
              <div>
                <v-card-title
                  class="text-h5"
                  v-text="item.title"
                ></v-card-title>

                <v-card-subtitle v-text="item.artist"></v-card-subtitle>

                <v-card-actions>
                  <v-btn
                    v-if="item.artist === 'Ellie Goulding'"
                    class="ml-2 mt-3"
                    fab
                    icon
                    height="40px"
                    right
                    width="40px"
                  >
                    <v-icon>mdi-play</v-icon>
                  </v-btn>

                  <v-btn
                    v-else
                    class="ml-2 mt-5"
                    outlined
                    rounded
                    small
                  >
                    START RADIO
                  </v-btn>
                </v-card-actions>
              </div>

              <v-avatar
                class="ma-3"
                size="125"
                tile
              >
                <v-img :src="item.src"></v-img>
              </v-avatar>
            </div>
          </v-card>
        </v-col> -->

                <v-col cols="12">
          <v-card class="elevation-0"
          >
            <v-card-title>
              Christmas Special
              <v-spacer></v-spacer>
                    <v-btn icon>
                    <v-icon>mdi-arrow-right</v-icon>
                </v-btn>
            </v-card-title>
            <v-card-actions>
                <v-row style="flex-wrap: nowrap;overflow-x: auto;">
                    <v-card v-for="(item, index) in christmasSpecial" :key="index" class="mx-auto elevation-0 px-2"
    max-width="178">

    <v-img
      :src="item.src"
    ></v-img>

                    </v-card>
                </v-row>
            </v-card-actions>
          </v-card>
        </v-col>

        <v-col cols="12">
          <v-card class="elevation-0"
          >
            <v-card-title>
              Editor's Choice Apps
              <v-spacer></v-spacer>
                    <v-btn icon>
                    <v-icon>mdi-arrow-right</v-icon>
                </v-btn>
            </v-card-title>
            <v-card-actions>
                <v-row style="flex-wrap: nowrap;overflow-x: auto;">
                    <v-card v-for="(item, index) in editorsChoice" :key="index" class="mx-auto elevation-0 px-2"
    max-width="120">

    <v-img
      :src="item.src"
       width="104"
      height="104"
    ></v-img>

    <v-card-title v-text="item.title" class="justify-center text-truncate apps-title" text-center
      wrap></v-card-title>
    <v-card-subtitle class="mx-2 apps-subtitle">
        <v-rating
          :value="1"
          color="amber"
          dense
          readonly
          size="14"
          length="1"
          style="display:inline-block"
        ></v-rating> <span style="color:#ffb74d"> {{ item.rating }}</span> | <span class="text-center"> {{ item.size }}</span></v-card-subtitle>
    <v-card-actions>
        <v-btn
        height="28px"
        depressed
        width="100%"
        >
        <v-icon>mdi-download</v-icon>
        </v-btn>
    </v-card-actions>


                    </v-card>
                </v-row>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-card>
</template>
<script>
  export default {
    data: () => ({
      exclusiveApps: [
        {
          src: require('../assets/images/sixth.jpg'),
          title: 'Teen Patti',
          size: '8 MB',
        },
        {
          src: require('../assets/images/seventh.jpg'),
          title: 'Team 11',
          size: '9 MB',
        },
        {
          src: require('../assets/images/eigth.jpg'),
          title: 'Kashkick',
          size: '14 MB',
        },
        {
          src: require('../assets/images/ninth.jpg'),
          title: 'Team 11',
          size: '9 MB',
        },
      ],
      christmasSpecial: [
        {
          src: require('../assets/images/first.png'),
          title: 'Teen Patti',
          size: '8 MB',
        },
        {
          src: require('../assets/images/second.png'),
          title: 'Team 11',
          size: '9 MB',
        },
        {
          src: require('../assets/images/third.png'),
          title: 'Kashkick',
          size: '14 MB',
        },
      ],
      editorsChoice: [
        {
          src: require('../assets/images/tenth.jpg'),
          title: 'Make Mytrip',
          size: '8 MB',
          rating: 4.2
        },
        {
          src: require('../assets/images/eleventh.jpg'),
          title: 'Akash Institute',
          size: '9 MB',
          rating: 4.2
        },
        {
          src: require('../assets/images/twelvth.jpg'),
          title: 'Farmiso',
          size: '14 MB',
          rating: 4.2
},
        {
          src: require('../assets/images/thirtheenth.jpg'),
          title: 'Olx: Buy & Sell',
          size: '14 MB',
          rating: 4.2
        },
      ],
    }),
  }
</script>t
<style>
    .apps-title {
        font-size: 1.2rem !important;
        padding: 3px 16px 0px 16px !important;
    }
    .apps-subtitle {
        font-size: 0.8rem !important;
        color: #252525bf;
    }
</style>