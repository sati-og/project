<template>
  <v-app>
   <first-page/>
  </v-app>
</template>

<script>
import FirstPage from './components/FirstPage.vue';

export default {
  name: 'App',

  components: {
    FirstPage
  },

  data: () => ({
    //
  }),
};
</script>
