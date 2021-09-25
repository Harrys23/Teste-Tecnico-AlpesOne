<template>
  <Header :isRequested="isRequested" />
  <Banner />
  <Products @handleQuotationRequest="handleQuotationRequest(request)" />
  <Whatsapp />
</template>

<script>
import Header from "../components/Header.vue";
import Banner from "../components/Banner.vue";
import Products from "../components/Products.vue";
import Whatsapp from "../components/Whatsapp.vue";

export default {
  name: "Body",
  components: {
    Banner,
    Products,
    Whatsapp,
    Header,
  },

  data() {
    return {
      isRequested: false,
    };
  },

  methods: {
    handleQuotationRequest() {
      this.isRequested = true;
    },
  },
};
</script>

<style lang="scss"></style>
