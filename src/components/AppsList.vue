<template>
  <v-card
    class="mx-auto"
  >
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
          <v-card class="elevation-0"
          >
            <v-card-title style="padding-left:0px;padding-right:0px;">
              <v-chip
      class="ma-2 app-chip"
      color="orange"
      label
      dark
      style="background-image: linear-gradient(to right, orange , red);"
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
                    <v-card v-for="(item, index) in exclusiveApps" :key="index" class="mx-auto elevation-0 px-1"
    max-width="80">

    <v-img
      :src="item.src"
     width="72"
      height="72" 
    ></v-img>

    <v-card-title v-text="item.title" class="text-truncate apps-title" text-center
      wrap></v-card-title>
    <div class="apps-subtitle"><span class="text-center mx-5"> {{ item.size }}</span></div>
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

     <v-col cols="12">
          <v-card class="elevation-0 social-card"
          >
            <v-card-title style="padding-left:0px;font-size:1rem !important">
               Your Friends Choice
              <v-spacer></v-spacer>
                <span style="font-size:0.8rem !important;opacity:0.7">More</span>
            </v-card-title>
            <div class="text-subtitle-1 pt-2 pb-3">
                  <v-img
                  width="230"
                    :src="require('../assets/images/frnds.png')"
                  ></v-img>
            </div>
            <v-card-actions>
                <v-row style="flex-wrap: nowrap;overflow-x: auto;">
                    <v-card v-for="(item, index) in friendsChoice" :key="index" class="mx-auto elevation-0 px-2 social-card-apps" width="120">

    <v-img
      :src="item.src"
     width="80"
      height="80"
      style="display:block;margin:auto;margin-top:10px"
    ></v-img>

    <v-card-title v-text="item.title" class="justify-center text-truncate apps-title width-100" text-center
      wrap></v-card-title>
    <div class="apps-subtitle width-100">
        <v-rating
          :value="1"
          color="amber"
          dense
          readonly
          size="14"
          length="1"
          style="display:inline-block"
        ></v-rating> <span style="color:#ffb74d"> 4.2 </span> | <span class="text-center"> {{ item.size }}</span><v-icon class="ml-5" small>mdi-download</v-icon></div>

                    </v-card>
                </v-row>
            </v-card-actions>
          </v-card>
        </v-col>

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
    max-width="170">

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
    max-width="80">

    <v-img
      :src="item.src"
       width="72"
      height="72"
    ></v-img>

    <v-card-title v-text="item.title" class="text-truncate apps-title" text-center
      wrap></v-card-title>
    <div class="apps-subtitle">
        <v-rating
          :value="1"
          color="amber"
          dense
          readonly
          size="14"
          length="1"
          style="display:inline-block"
        ></v-rating> <span style="color:#ffb74d"> {{ item.rating }}</span> | <span class="text-center"> {{ item.size }}</span></div>
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
          title: 'Spin and Win',
          size: '9 MB',
        },
        {
          src: require('../assets/images/eigth.jpg'),
          title: 'Kashkick',
          size: '14 MB',
        },
        {
          src: require('../assets/images/ninth.jpg'),
          title: 'My Team 11',
          size: '9 MB',
        },
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
      friendsChoice: [
        {
          src: require('../assets/images/fourth.png'),
          title: 'Candy Crush Saga',
          size: '18 MB',
        },
        {
          src: require('../assets/images/fifth.png'),
          title: 'Amazon music',
          size: '18 MB',
        },
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
      ]
    }),
  }
</script>t
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
</style>