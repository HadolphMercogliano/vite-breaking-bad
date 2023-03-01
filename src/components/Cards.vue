<script>
import { store } from "../data/store";
export default {
  data() {
    return {
      store,
    };
  },
};
</script>
<template>
  <div
    class="col d-flex align-items-stretch"
    v-for="card in store.CardsList">
    <div class="my-card">
      <img
        class="img-fluid"
        :src="card.card_images[0].image_url"
        alt="" />
      <div class="card-text text-center pt-3">
        <p class="fw-bolder text-light">{{ card.name.toUpperCase() }}</p>
        <p>{{ card.archetype }}</p>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../assets/scss/partials/mixins" as *;
.my-card {
  @include bg-orange;

  .card-text {
    font-size: 0.7rem;
  }
}
</style>
