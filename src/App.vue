<script>
import axios from "axios";

import "bootstrap/dist/css/bootstrap.min.css";
import HeaderApp from "./components/HeaderApp.vue";
import MainApp from "./components/MainApp.vue";
import { store } from "./data/store";
import SearchBar from "./components/SearchBar.vue";
export default {
  data() {
    return {
      store,
    };
  },
  components: { HeaderApp, MainApp, SearchBar },

  methods: {
    FilterforType(type) {
      axios.get(`${store.endpoint}&${type}`).then((response) => {
        console.log(response);
        store.CardsList = response.data.data;
        console.log(store.CardsList);
        store.foundItems = response.data.meta.total_rows;
        console.log(store.foundItems);
      });
      // axios
      //   .get(
      //     `https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0&type=${type}`
      //   )
      //   .then((response) => {
      //     console.log(response);
      //   });
    },
  },

  // chiamata axios a yu-gi-oh API
  created() {
    axios.get(`${store.endpoint}`).then((response) => {
      // console.log(response);
      store.CardsList = response.data.data;
      // console.log(store.CardsList);
      store.foundItems = response.data.meta.total_rows;
      // console.log(store.foundItems);
    });
  },
};
</script>

<template>
  <HeaderApp />
  <div class="bg-orange px-5">
    <SearchBar @type-choise="FilterforType" />
    <div class="bg-white p-5">
      <div class="container">
        <MainApp />
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "./assets/scss/style.scss" as *;
@use "./assets/scss/partials/mixins" as *;
.bg-orange {
  @include bg-orange;
}
.bg-white {
  @include bg-white;
}
.container {
  background-color: white;
}
</style>
