<script>
//Importo i Componenti Figli
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";

//Importo Axios per recuperare i dati dall'API
import axios from "axios";

//Collego il file JS che contiene i dati delle carte
import { store } from "./store.js";

export default {
  data() {
    return {
      store,
      apiUri:
        "https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=laval&num=10&offset=0",
    };
  },
  components: {
    AppHeader,
    AppMain,
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
    //Filtro le carte in base al valore selezionato
    searchCard(value) {
      axios
        .get(this.apiUri, {
          params: {
            archetype: value,
          },
        })
        .then((res) => {
          console.log(res);
        });
    },
  },

  created() {
    this.getCards();
    this.searchCard();
  },
};
</script>

<template>
  <AppHeader />
  <AppMain @searchedCard="searchCard" />
</template>

<style lang="scss"></style>
