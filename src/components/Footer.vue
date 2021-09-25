<template>
  <div class="footerContainer">
    <p>
      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed a elementum
      orci, vitae commodo nibh. In vitae convallis nisl. Morbi rhoncus mattis
      purus sed commodo. Integer rhoncus ex risus. Proin efficitur elit nunc, ut
      pulvinar massa egestas in. Fusce quis quam viverra, pretium quam ac,
      consectetur lectus.
    </p>
    <div class="separator" />
    <p>© Copyright © 2021 Lorem ipsum dolor sit amet.</p>
    <div class="logo">
      <p>Feito por:</p>
      <img :src="'/assets/imgs/logos/logo-alpes.png'" alt="Logo da Alpes One" />
    </div>
  </div>
</template>

<script>
export default {
  name: "Footer",
};
</script>

<style lang="scss">
@import "@/styles/_variables.scss";

.footerContainer {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;

  margin-top: 3rem;
  padding: 2rem;

  width: 100vw;
  height: 25rem;
  gap: 1rem;

  background-color: $footer;

  p {
    font-size: 1rem;
    font-weight: normal;
    color: $text;
    text-align: center;

    max-width: 75%;
  }

  .separator {
    height: 0.1rem;
    width: 100%;
    background-color: $separator;
  }

  .logo {
    display: flex;
    align-items: center;

    img {
      margin-left: 1rem;
    }
  }
}
</style>
