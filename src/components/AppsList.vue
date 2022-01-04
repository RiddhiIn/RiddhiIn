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
            <v-card-title style="padding-left:0px;">
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

     <v-col cols="12">
          <v-card class="elevation-0 social-card"
          >
            <v-card-title style="padding-left:0px;">
               Your Friends Choice
              <v-spacer></v-spacer>
                    <v-btn text>
                    <v-text>More</v-text>
                </v-btn>
            </v-card-title>
            <v-card-actions>
                <v-row style="flex-wrap: nowrap;overflow-x: auto;">
                    <v-card v-for="(item, index) in exclusiveApps" :key="index" class="mx-auto elevation-0 px-2 social-card-apps"
    max-width="120">

    <v-img
      :src="item.src"
     width="104"
      height="104" 
    ></v-img>

    <v-card-title v-text="item.title" class="justify-center text-truncate apps-title" text-center
      wrap></v-card-title>
    <v-card-subtitle class="apps-subtitle">
        <v-rating
          :value="1"
          color="amber"
          dense
          readonly
          size="14"
          length="1"
          style="display:inline-block"
        ></v-rating> <span style="color:#ffb74d"> 4.2 </span> | <span class="text-center"> {{ item.size }}</span><v-icon class="ml-1">mdi-download</v-icon></v-card-subtitle>

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
<style scoped>
    .v-card__title {
        font-size: 1.2rem !important;
    }
    .apps-title {
        font-size: 1rem !important;
        padding: 3px 16px 0px 16px !important;
    }
    .apps-subtitle {
        font-size: 0.7rem !important;
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
</style>