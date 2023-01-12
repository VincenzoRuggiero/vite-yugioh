<script>
//Collego il file JS che contiene i dati delle carte
import { store } from "../store.js";
//Importo Axios per recuperare i dati dall'API
import axios from "axios";

export default {
  name: "CardComp",

  data() {
    return {
      store,
    };
  },
  methods: {
    //Recupero le informazioni per le carte tramite l'API fornita
    getCards() {
      axios
        .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=10&offset=0")
        .then((response) => {
          this.store.cardsList = response.data.data;
        });
    },
  },
  created() {
    this.getCards();
  },
};
</script>

<template>
  <div v-for="card in store.cardsList" class="single-card">
    <img :src="card.card_images[0].image_url" alt="" />
    <p class="card-title">{{ card.name }}</p>
    <p class="card-type">{{ card.archetype }}</p>
  </div>
</template>

<style lang="scss">
.single-card {
  width: calc(100% / 5 - 1rem);
  background-color: #d48f38;
  margin: 0 0.5rem 1rem;
  text-align: center;

  img {
    width: 100%;
  }

  .card-title {
    color: white;
    font-weight: bold;
    padding: 1rem;
  }

  .card-type {
    padding: 1rem 0 0.5rem;
  }
}
</style>
