<script>
import { store } from "../data/store";
import Cards from "./Cards.vue";
export default {
  data() {
    return {
      store,
    };
  },
  components: { Cards },
};
</script>

<template>
  <p>FOUND {{ store.CardsList.length }} CARDS</p>
  <div class="row row-cols-5">
    <Cards />
  </div>
</template>

<style lang="scss" scoped>
@use "../assets/scss/style.scss" as *;
</style>
