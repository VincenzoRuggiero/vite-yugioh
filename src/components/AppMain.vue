<script>
//Collego il file JS che contiene i dati delle carte
import { store } from "../store.js";

//Importo Axios per recuperare i dati dall'API
import axios from "axios";
export default {
  name: "AppMain",
  data() {
    return {
      store,
      cardsInfo: [],
    };
  },

  methods: {
    //recupero le informazioni per le carte tramite l'API fornita
    getCards() {
      axios
        .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=10&offset=0")
        .then((response) => {
          this.cardsInfo = response.data;
        });
    },
  },

  created() {
    this.getCards();
  },
};
</script>

<template>
  <p v-for="card in cardsInfo">
    {{ card.name }}
  </p>
</template>

<style lang="scss"></style>
