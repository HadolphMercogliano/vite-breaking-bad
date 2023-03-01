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
    class="col"
    v-for="card in store.CardsList">
    <img
      class="img-fluid"
      :src="card.card_images[0].image_url"
      alt="" />
    <div class="card-text text-center">
      <p>{{ card.name.toUpperCase() }}</p>
      <p>{{ card.archetype }}</p>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.col {
}
</style>
