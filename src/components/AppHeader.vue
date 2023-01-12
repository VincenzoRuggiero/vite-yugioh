<script>
export default {};
</script>

<template lang="">
  <div class="header">
    <img
      src="https://upload.wikimedia.org/wikipedia/commons/1/11/Yu-Gi-Oh%21_%28Logo%29.jpg"
      alt="Site's logo" />
    <h1>Yu-Gi-Oh Api</h1>
  </div>
</template>

<style lang="scss">
@use "../styles/general.scss";
.header {
  background-color: white;
  padding: 0.5rem 1rem;

  img {
    width: 4rem;
    margin-right: 0.5rem;
  }

  h1 {
    display: inline-block;
    font-weight: 400;
    font-size: 1.5rem;
  }
}
</style>
