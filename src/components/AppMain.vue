<script>
import CardComp from "./CardComp.vue";
import { store } from "../store.js";

export default {
  name: "AppMain",
  components: {
    CardComp,
  },
  data() {
    return {
      store,
    };
  },
};
</script>

<template>
  <header class="header">
    <img
      src="https://upload.wikimedia.org/wikipedia/commons/1/11/Yu-Gi-Oh%21_%28Logo%29.jpg"
      alt="Site's logo" />
    <h1>Yu-Gi-Oh Api</h1>
  </header>
  <main>
    <div class="total-cards">Found {{ store.cardsList.length }} cards</div>
    <div class="cards-container">
      <CardComp />
    </div>
  </main>
</template>

<style lang="scss">
@use "../styles/general.scss";

header {
  background-color: white;
  padding: 0.5rem 1rem;

  img {
    width: 4rem;
    margin-right: 0.5rem;
  }

  h1 {
    display: inline-block;
    font-weight: 400;
    font-size: 1.5rem;
  }
}

main {
  background-color: #d48f38;
  padding: 4rem;

  .total-cards {
    background-color: #202528;
    color: white;
    padding: 0.7rem 1rem;
  }

  .cards-container {
    background-color: white;
    margin: 0 auto;
    padding: 1.5rem;
    display: flex;
    flex-wrap: wrap;
  }
}
</style>
