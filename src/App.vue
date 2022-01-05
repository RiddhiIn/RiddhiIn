<style>
  ::-webkit-scrollbar {
    display: none;
  }

  /* Hide scrollbar for IE, Edge and Firefox */
  #app {
    -ms-overflow-style: none;  /* IE and Edge */
    scrollbar-width: none;  /* Firefox */
  }
</style>
<template>
  <v-app>
    <v-content>
      <AppsList/>
    </v-content>
  </v-app>
</template>

<script>
import AppsList from './components/AppsList';

export default {
  name: 'App',
  components: {
    AppsList,
  },
  data: () => ({
    //
  }),
};
</script>
