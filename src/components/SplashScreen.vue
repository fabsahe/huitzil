<template>
  <VueSplash
    :show="true"
    :logo="logo"
    title="BIENVENIDO"
    color="#00bfa5"
    :size="300"
    :fixed="true"
  />
</template>
 
<script>
import VueSplash from "./VueSplash.vue";
import HuitzilLogo from "../assets/huitzil.png";
 
export default {
  name: "SplashScreen",

  components: {
    VueSplash
  },

  computed: {
    logo() {
      return HuitzilLogo;
    }
  }
}
</script>

<style>

</style>