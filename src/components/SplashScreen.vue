<template>
  <VueSplash
    :show="true"
    :logo="logo"
    title="BIENVENIDO"
    color="#00bfa5"
    :size="220"
    :fixed="true"
  />
</template>
 
<script>
import VueSplash from "./VueSplash.vue";
import HuitzilLogo from "../assets/huitzil-big.png";
 
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