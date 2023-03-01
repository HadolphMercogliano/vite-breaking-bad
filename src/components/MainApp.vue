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
  <div>
    <p class="bg-dark text-light fw-semibold m-0">
      FOUND {{ store.CardsList.length }} CARDS
    </p>
    <div class="row row-cols-5 gy-3">
      <Cards />
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../assets/scss/style.scss" as *;
</style>
