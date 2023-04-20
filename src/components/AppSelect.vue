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
  <div class="wrap">
    <p>Choose a category:</p>
    <select
      class="select"
      v-model="type"
      id=""
      @change="$emit('searchedCard', type)">
      <option value="alien">Alien</option>
      <option value="laval">Laval</option>
      <option value="vylon">Vylon</option>
      <option value="inzektor">Inzektor</option>
      <option value="umi">Umi</option>
      <option value="gusto">Gusto</option>
    </select>
  </div>
</template>

<style lang="scss">
.wrap {
  margin-left: 1rem;
  display: flex;
  align-items: center;
}
.select {
  padding: 0.3rem;
  margin-left: 1rem;
}
</style>
