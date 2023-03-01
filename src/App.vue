<script>
import axios from "axios";

import "bootstrap/dist/css/bootstrap.min.css";
import HeaderApp from "./components/HeaderApp.vue";
import MainApp from "./components/MainApp.vue";
import { store } from "./data/store";
export default {
  data() {
    return {
      store,
    };
  },
  components: { HeaderApp, MainApp },

  // chiamata axios a yu-gi-oh API
  created() {
    axios
      .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
      .then((response) => {
        console.log(response);
        store.CardsList = response.data.data;
        console.log(store.CardsList);
      });
  },
};
</script>

<template>
  <HeaderApp />
  <div class="bg-orange p-5">
    <div class="bg-light py-4">
      <div class="container">
        <MainApp />
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "./assets/scss/style.scss" as *;
.bg-orange {
  background-color: coral;
}
.container {
  background-color: white;
}
</style>
