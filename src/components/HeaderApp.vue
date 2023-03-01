<script>
export default {
  data() {
    return {};
  },
};
</script>

<template>
  <div class="py-3 px-5 d-flex align-items-center bg-white">
    <img
      class="logo"
      src="../assets/img/index.jpg"
      alt="" />
    <h1 class="d-inline-block">Yu-Gi-Oh API</h1>
  </div>
</template>

<style lang="scss" scoped>
@use "../assets/scss/partials/mixins" as *;
.logo {
  width: 100px;
  margin-right: 30px;
}
.bg-white {
  @include bg-white;
}
</style>
