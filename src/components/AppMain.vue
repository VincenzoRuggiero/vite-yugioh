<script>
//Importo Axios per recuperare i dati dall'API
import axios from "axios";

//Collego il file JS che contiene i dati delle carte
import { store } from "../store.js";

export default {
  name: "AppMain",

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
  <p v-for="card in store.cardsList">
    {{ card.name }}
  </p>
</template>

<style lang="scss"></style>
