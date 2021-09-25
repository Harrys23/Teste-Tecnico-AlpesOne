<template>
  <div class="productsTittle">
    <h1>Escolha sua BMW</h1>
  </div>
  <div class="productsList">
    <div v-for="cars in cars" :key="cars.id" class="products">
      <img :src="cars.picture" :alt="cars.name" />
      <h2>BMW {{ cars.name }}</h2>
      <div class="productsButtons">
        <button @click="showModal">Cotação</button>
        <button>Ligar</button>
      </div>
      <div class="social">
        <p>Compartilhe:</p>
        <svg
          id="Camada_1"
          data-name="Camada 1"
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 24 24"
        >
          <path
            d="M10,21.5h3.49V13h2.71l.44-3.37H13.45V7.29a1.86,1.86,0,0,1,.29-1.19,1.72,1.72,0,0,1,1.37-.44H16.9v-3a18.8,18.8,0,0,0-2.6-.15,4.31,4.31,0,0,0-3.15,1.17A4.45,4.45,0,0,0,10,7V9.63H7.1V13H10Z"
          />
        </svg>
        <svg
          id="Camada_1"
          data-name="Camada 1"
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 24 24"
        >
          <path
            id="Caminho_6"
            data-name="Caminho 6"
            d="M18.66,5.26a9.81,9.81,0,0,1,2.1,3.07,9.15,9.15,0,0,1-.55,8.29,9.72,9.72,0,0,1-3.48,3.44A9.24,9.24,0,0,1,12,21.33h0a9.11,9.11,0,0,1-4.5-1.15l-5,1.32,1.36-4.88a9.06,9.06,0,0,1-1.28-4.71,9.05,9.05,0,0,1,1.28-4.7A9.58,9.58,0,0,1,7.29,3.77a9.32,9.32,0,0,1,8.29-.55A9.79,9.79,0,0,1,18.66,5.26ZM12,19.76a7.66,7.66,0,0,0,3.94-1.06,8.06,8.06,0,0,0,2.91-2.86,7.55,7.55,0,0,0,1.08-3.93,7.2,7.2,0,0,0-.64-3,8.23,8.23,0,0,0-1.76-2.57A7.87,7.87,0,0,0,15,4.66a7.88,7.88,0,0,0-6.92.46A8,8,0,0,0,5.21,8a7.71,7.71,0,0,0,.17,8.08l.17.3-.8,2.88,3-.76.3.17A7.56,7.56,0,0,0,12,19.76Zm4.28-5.9.13.09a.68.68,0,0,1,.34.21,1.19,1.19,0,0,1,0,.42,2.39,2.39,0,0,1-.17.7,1.75,1.75,0,0,1-.68.72,2.07,2.07,0,0,1-.91.4,3.7,3.7,0,0,1-1.15,0,9.51,9.51,0,0,1-1.7-.59,9.65,9.65,0,0,1-3.94-3.47l-.08-.09a4.26,4.26,0,0,1-.93-2.41A2.68,2.68,0,0,1,8,7.92l0,0a.9.9,0,0,1,.63-.3h.51a.55.55,0,0,1,.28.07A.63.63,0,0,1,9.63,8l.72,1.74a.47.47,0,0,1,0,.43,3,3,0,0,1-.55.76.83.83,0,0,0-.21.28c0,.07,0,.14.08.23a5.49,5.49,0,0,0,1.4,1.74,10.32,10.32,0,0,0,1.78,1.06c.23.12.4.1.51,0a11.89,11.89,0,0,0,.76-.93c.06-.11.13-.17.21-.17a1.36,1.36,0,0,1,.3,0c.23.08.76.34,1.61.77Z"
          />
        </svg>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Products",
  components: {},

  data() {
    return {
      cars: [
        {
          id: 0,
          name: "Série 1",
          picture: "/assets/imgs/veiculos/serie1.png",
        },
        {
          id: 1,
          name: "Série 2",
          picture: "/assets/imgs/veiculos/serie2.png",
        },
        {
          id: 2,
          name: "Série 3",
          picture: "/assets/imgs/veiculos/serie-3.png",
        },
        {
          id: 3,
          name: "Série 4",
          picture: "/assets/imgs/veiculos/serie-4.png",
        },
        {
          id: 4,
          name: "M3",
          picture: "/assets/imgs/veiculos/m3.png",
        },
        {
          id: 5,
          name: "M5",
          picture: "/assets/imgs/veiculos/m5.png",
        },
        {
          id: 6,
          name: "X2",
          picture: "/assets/imgs/veiculos/x2.png",
        },
        {
          id: 7,
          name: "Z4",
          picture: "/assets/imgs/veiculos/z4.png",
        },
      ],
      isModalVisible: false,
    };
  },

  methods: {
    showModal() {
      this.$emit("handleQuotationRequest", true);
    },
  },
};
</script>

<style lang="scss" scoped>
@import "@/styles/_variables.scss";

.productsTittle {
  display: flex;
  justify-content: center;
  align-items: center;

  margin-top: 3rem;

  h1 {
    font-size: 2rem;
    font-weight: normal;
  }
}

.productsList {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100vw;

  margin: auto;
  max-width: 169rem;

  gap: 3rem;
  flex-wrap: wrap;

  .products {
    display: flex;
    flex-direction: column;

    img {
      transition: 0.3s;

      &:hover {
        opacity: 50%;
        cursor: pointer;
      }
    }

    h2 {
      font-weight: normal;
      font-size: 2rem;
    }

    .productsButtons {
      display: flex;
      justify-content: space-between;
      margin-top: 2rem;
      margin-bottom: 2rem;

      button {
        background-color: $blueButton;
        border: none;
        font-size: 1.2rem;
        font-weight: bold;
        padding: 1rem 0;
        width: 45%;
        color: $bg;
        transition-duration: 30ms;

        &:hover {
          background-color: $darkBlue;
          cursor: pointer;
        }

        &:nth-child(2) {
          background-color: $gray;
        }
      }
    }

    .social {
      display: flex;
      justify-content: flex-start;
      align-items: center;

      gap: 1rem;

      p {
        font-size: 1.2rem;
        color: $gray;
      }

      svg {
        width: 2.4rem;
        fill: $gray;
        transition: 0.3s;

        &:hover {
          fill: $blueButton;
          cursor: pointer;
        }
        &:last-child:hover {
          fill: $greenWp;
          cursor: pointer;
        }
      }
    }
  }
}

@media (min-width: 768px) {
  .productsList .products .productsButtons button {
    width: 100%;

    &:last-child {
      display: none;
    }
  }
}
</style>
