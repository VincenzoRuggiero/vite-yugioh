<script>
//Importo i Componenti Figli
import AppHeader from "./components/AppHeader.vue";
import AppSelect from "./components/AppSelect.vue";
import AppMain from "./components/AppMain.vue";

//Importo Axios per recuperare i dati dall'API
import axios from "axios";

//Collego il file JS che contiene i dati delle carte
import { store } from "./store.js";

export default {
  data() {
    return {
      store,
      apiUri: "https://db.ygoprodeck.com/api/v7/cardinfo.php",
    };
  },
  components: {
    AppHeader,
    AppSelect,
    AppMain,
  },
  methods: {
    //Filtro le carte in base al valore selezionato
    searchCard(value) {
      axios
        .get(this.apiUri, {
          params: {
            archetype: value,
            num: 10,
            offset: 0,
          },
        })
        .then((response) => {
          this.store.cardsList = response.data.data;
        });
    },
  },

  created() {
    this.searchCard("");
  },
};
</script>

<template>
  <AppHeader />
  <AppSelect @searchedCard="searchCard" />
  <AppMain />
</template>

<style lang="scss"></style>
