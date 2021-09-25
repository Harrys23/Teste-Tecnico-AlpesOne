<template>
  <div v-if="isMobile" class="bannerMobileContainer">
    <img :src="'/assets/imgs/banners/mobile-banner.png'" alt="Banner" />
  </div>
  <div v-if="!isMobile" class="bannerDesktopContainer">
    <img :src="'/assets/imgs/banners/desktop-.jpg'" alt="Banner" />
    <div>
      <QForm />
    </div>
  </div>
</template>

<script>
import QForm from "./QForm.vue";
export default {
  name: "Banner",
  components: {
    QForm,
  },

  data() {
    if (window.innerWidth < 768) {
      return {
        isMobile: true,
      };
    }
    return {
      isMobile: false,
    };
  },
};
</script>

<style lang="scss" scoped>
.bannerMobileContainer {
  display: flex;

  margin-top: 10.5rem;

  img {
    width: 100%;
  }
}

.bannerDesktopContainer {
  display: flex;
  width: 100vw;
  margin-top: 10rem;

  img {
    width: 100vw;
  }
}
</style>
