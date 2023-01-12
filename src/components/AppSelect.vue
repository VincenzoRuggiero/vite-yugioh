<script>
export default {
  name: "AppSelect",
  data() {
    return {
      type: "",
    };
  },
};
</script>

<template>
  <select v-model="type" id="" @change="$emit('searchedCard', type)">
    <option value="alien">Alien</option>
    <option value="laval">Laval</option>
    <option value="vylon">Vylon</option>
    <option value="inzektor">Inzektor</option>
    <option value="umi">Umi</option>
    <option value="gusto">Gusto</option>
  </select>
</template>

<style lang=""></style>
