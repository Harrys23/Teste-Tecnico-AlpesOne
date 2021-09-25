<template>
  <Body />
  <Footer />
</template>

<script>
import Body from "./pages/Body.vue";
import Footer from "./components/Footer.vue";

export default {
  name: "App",
  components: {
    Body,
    Footer,
  },
};
</script>

<style lang="scss">
@import "./styles/global.scss";
</style>
