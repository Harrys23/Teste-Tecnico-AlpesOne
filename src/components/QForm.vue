<template>
  <transition name="modaFade">
    <div class="modalBg" @click="close">
      <div class="formContainer">
        <div class="formBody">
          <div class="formTittle">
            <svg
              id="Camada_1"
              data-name="Camada 1"
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 24 24"
            >
              <path
                id="Caminho_126"
                data-name="Caminho 126"
                d="M21.45,9.26l-1.57.33L22,11.19v7.23a1.13,1.13,0,0,1-1.11,1.1H19.23a1.12,1.12,0,0,1-1.11-1.11v-.55H5.88v.55a1.12,1.12,0,0,1-1.11,1.11H3.11A1.11,1.11,0,0,1,2,18.41V11.18l2.12-1.6L2.56,9.25a.73.73,0,0,1-.46-.32A1,1,0,0,1,2,8.47.65.65,0,0,1,2.16,8a.59.59,0,0,1,.49-.2H4.77a14.19,14.19,0,0,1,1.94-2.5,3.7,3.7,0,0,1,2.62-.83h5.34a3.7,3.7,0,0,1,2.62.83,14.19,14.19,0,0,1,1.94,2.5h2.12a.59.59,0,0,1,.49.2.65.65,0,0,1,.16.45,1,1,0,0,1-.1.46A.79.79,0,0,1,21.45,9.26ZM7,14.5V14a1.66,1.66,0,0,0-1.66-1.66H2.55v.55A1.49,1.49,0,0,0,3.17,14a2.11,2.11,0,0,0,1.34.48ZM5.88,9H18.12A12.31,12.31,0,0,0,17,6.64a2.22,2.22,0,0,0-2-1H9a2.21,2.21,0,0,0-2,1A11.74,11.74,0,0,0,5.88,9ZM12,12.84c0-.15-.1-.28-.31-.39a1.26,1.26,0,0,0-.54-.16H8.61a1,1,0,0,0-.52.15.44.44,0,0,0-.26.4A1.47,1.47,0,0,0,8.4,14.1a1.87,1.87,0,0,0,1.09.4h1.66a1.13,1.13,0,0,0,.54-.16c.21-.11.31-.24.31-.39Zm2.51,1.66a1.87,1.87,0,0,0,1.09-.4,1.44,1.44,0,0,0,.57-1.26.44.44,0,0,0-.26-.4,1,1,0,0,0-.52-.15H12.85a1.26,1.26,0,0,0-.54.16c-.21.11-.31.24-.31.39V14c0,.15.1.28.31.39a1.13,1.13,0,0,0,.54.16Zm4.17-2.21A1.66,1.66,0,0,0,17,14v.55h2.47A1.17,1.17,0,0,0,20.55,14a2.06,2.06,0,0,0,.34-1.18v-.55Z"
              />
            </svg>
            <p>Solicitar cotação</p>
          </div>
          <form>
            <div class="input">
              <input type="text" placeholder="" id="name" />
              <label for="name">Nome</label>
            </div>
            <div class="input">
              <input type="email" placeholder="" id="email" />
              <label for="email">E-mail</label>
            </div>
            <div class="input">
              <input type="tel" placeholder="" id="tel" />
              <label for="tel">Telefone</label>
            </div>

            <div class="input">
              <select id="select" name="Modelo">
                <option disabled selected value="">Modelo</option>
                <option value="m3">M3</option>
                <option value="m5">M5</option>
                <option value="serie-1">Série 1</option>
                <option value="serie-2">Série 2</option>
                <option value="serie-3">Série 3</option>
                <option value="serie-4">Série 4</option>
                <option value="x2">X2</option>
                <option value="z4">Z4</option>
              </select>
              <svg
                id="Camada_1"
                data-name="Camada 1"
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 24 24"
              >
                <path
                  d="M3.33,8.87a.7.7,0,0,1,0-1L4.42,6.77a.65.65,0,0,1,.93,0h0L12,13.52l6.63-6.75a.66.66,0,0,1,.93,0l0,0L20.67,7.9a.7.7,0,0,1,0,1l-8.2,8.36a.65.65,0,0,1-.92,0l0,0Z"
                />
              </svg>
            </div>

            <div class="input">
              <textarea placeholder="" id="msg"></textarea>
              <label for="msg">Mensagem</label>
            </div>

            <div class="checkbox">
              <input type="checkbox" id="checkbox" />
              <label for="checkbox"
                >Aceito a&nbsp;
                <p>Política de Privacidade.</p></label
              >
            </div>

            <button @click.prevent="close" class="submitButton" type="submit">
              Enviar
            </button>
          </form>
        </div>
      </div>
    </div>
  </transition>
</template>

<script>
export default {
  name: "QForm",

  methods: {
    close() {
      this.$emit("close");
    },
  },
};
</script>

<style lang="scss" scoped>
@import "@/styles/_variables.scss";

.modalBg {
  position: fixed;
  top: 45px;
  bottom: 0;
  left: 0;
  right: 0;
  background-color: rgba(0, 0, 0, 0.3);
  display: flex;
  justify-content: center;
  align-items: center;

  .formContainer {
    position: absolute;
    top: 0;
    display: flex;
    flex-direction: column;
    width: 100%;
    overflow-y: hidden;

    background-color: $bg;

    button {
      border: none;
      width: calc(100% - 32px);
      height: 4.5rem;
      margin-bottom: 2rem;

      font-weight: bold;
      font-size: 1.4rem;

      background-color: $blueButton;
      color: $bg;
    }

    .formBody {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 3rem;

      .formTittle {
        display: flex;
        justify-content: center;
        padding-top: 3rem;
        gap: 1rem;

        svg {
          width: 2.8rem;
          fill: $blueButton;
        }

        p {
          font-size: 2rem;
        }
      }

      form {
        display: flex;
        flex-direction: column;
        align-items: center;
        align-content: center;

        width: 100%;

        gap: 3rem;

        .input {
          position: relative;
          width: calc(100% - 32px);

          margin: auto;

          input,
          select,
          textarea {
            outline: none;
            border: 0;
            border-bottom: 1px solid $gray;
            background-color: transparent;

            color: $gray;

            width: 100%;
            height: 3rem;
          }

          textarea {
            resize: none;
          }

          select {
            appearance: none;
          }

          svg {
            width: 2rem;
            height: 2rem;
            position: absolute;
            fill: $gray;

            transition: 0.3s;

            top: 0.4rem;
            right: 0;
          }

          label {
            position: absolute;
            top: 0;
            left: 0;
            font-size: 1.4rem;
            color: $gray;

            transition: 0.3s;
          }

          input,
          textarea,
          select {
            &:hover {
              border-bottom: 2px solid $gray;
            }
            &:focus ~ label,
            &:not(:placeholder-shown) ~ label {
              top: -10px;
              font-size: 0.7rem;
            }
            &:focus {
              border-bottom: 2px solid $blueButton;
            }
          }

          select {
            &:focus ~ svg {
              transform: rotateZ(180deg);
              fill: $blueButton;
            }
          }
        }

        .checkbox {
          width: calc(100% - 32px);
          margin: auto;

          > input,
          label {
            height: 1.2rem;
            display: inline-flex;
          }

          label,
          p {
            font-size: 1.2rem;
          }

          label {
            margin-left: 1rem;
          }

          input:hover ~ label {
            color: $blueButton;
          }
        }
      }
    }
  }
}
</style>
