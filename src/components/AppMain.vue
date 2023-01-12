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
      type: "",
    };
  },
};
</script>

<template>
  <main>
    <select name="" id="" @change="$emit('searchedCard', type)">
      <option value="Alien">Alien</option>
      <option value="Laval">Laval</option>
      <option value="Vylon">Vylon</option>
      <option value="Inzektor">Inzektor</option>
      <option value="Umi">Umi</option>
      <option value="Gusto">Gusto</option>
    </select>

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
    padding: 0 1.5rem 2rem;
    display: flex;
    flex-wrap: wrap;
  }
}
</style>
