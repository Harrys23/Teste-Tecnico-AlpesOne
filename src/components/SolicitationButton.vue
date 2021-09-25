<template>
  <div class="container" :class="{ clicked: isModalVisible }">
    <button v-if="!isModalVisible" @click="showModal">
      Solicite uma cotação
    </button>
    <button v-if="isModalVisible || isRequested" @click="closeModal">
      Minimizar
    </button>
  </div>
  <QForm v-show="isModalVisible || isRequested" @close="closeModal" />
</template>

<script>
import QForm from "./QForm.vue";

export default {
  name: "SolicitationButton",
  components: {
    QForm,
  },

  props: {
    isRequested: Boolean,
  },

  data() {
    return {
      isModalVisible: false,
    };
  },

  methods: {
    showModal() {
      this.isModalVisible = true;
    },
    closeModal() {
      this.isModalVisible = false;
    },
  },
};
</script>

<style lang="scss" scoped>
@import "@/styles/_variables.scss";

.container {
  display: flex;
  justify-content: center;
  align-items: center;

  position: fixed;
  top: 60px;
  height: 4.5rem;
  width: 100vw;

  transition: 0.3s;

  button {
    color: $bg;
    height: 100%;
    width: 100%;
    background-color: $blueButton;
    border: none;
    font-weight: bold;
    font-size: 1.4rem;
    cursor: pointer;

    transition: 0.3s;
    &:hover {
      background-color: $darkBlue;
    }
  }

  &.clicked {
    top: 0;

    button {
      background-color: $gray;
    }
  }
}

@media (min-width: 768px) {
  .container {
    width: 25.5rem;
    height: 6rem;
    top: 0;
    right: 0;
  }
}
</style>
