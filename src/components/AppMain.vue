<script>
import { store } from "../store.js";

export default {
  name: "AppMain",
  data() {
    return {
      store,
    };
  },
};
</script>

<template>
  <div>{{ store.text }}</div>
</template>

<style lang="scss"></style>
