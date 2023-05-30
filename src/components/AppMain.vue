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
  <main>
    <div class="total-cards">Found {{ store.cardsList.length }} cards</div>
    <div class="cards-container">
      <CardComp />
    </div>
  </main>
</template>

<style lang="scss">
@use "../styles/general.scss";

main {
  background-color: #d48f38;
  padding: 4rem;

  .total-cards {
    background-color: #202528;
    color: white;
    padding: 1rem;
  }

  .cards-container {
    background-color: white;
    margin: 0 auto;
    padding: 2rem 1.5rem 2rem;
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
  }
}
</style>
