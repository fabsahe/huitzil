<template>
  <v-app>
    <SplashScreen v-if="isLoading"/>

    <StartMenu v-if="!isLoading"/>

  </v-app>
</template>

<script>
import StartMenu from './components/StartMenu';
import SplashScreen from './components/SplashScreen';

export default {
  name: 'App',

  components: {
    SplashScreen,
    StartMenu,
  },

  data: () => ({
    isLoading: true,
  }),

  mounted() {
    setTimeout(() => {
      this.isLoading = false;
    }, 2500);
  }


};
</script>

<style>
.vue-splash__text {
  margin-top: 50px;
  font-size: 2rem;
  text-align: center;
}
</style>