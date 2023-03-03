<script>
import cardTypes from "../data/cardTypes";
export default {
  data() {
    return {
      cardTypes,
      message: "hello searchbar",
    };
  },
  emits: ["type-choise"],
};
</script>
<template>
  <div class="py-4 d-flex justify-content-center align-items-center">
    <label
      class="pe-3"
      for="Type"
      >Filter for
    </label>
    <select
      id="Type"
      class="form-select w-25"
      aria-label="Default select example">
      <option selected>TYPE</option>
      <optgroup
        :label="cardType.category"
        v-for="cardType of cardTypes">
        <option
          v-for="(cType, index) in cardType.typesList"
          @click="$emit('type-choise', cardType.typesList[index])"
          :value="cardType.typesList[index]">
          {{ cardType.typesList[index] }}
        </option>
      </optgroup>
    </select>
  </div>
</template>

<style lang="scss" scoped></style>
