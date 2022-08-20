<template>
  <div id="app">
    <display-selection></display-selection>
    <dog-button></dog-button>
    <cat-button></cat-button>
  </div>
</template>

<script>
import DisplaySelection from "@/components/DisplaySelection.vue";
import DogButton from "@/components/DogButton.vue";
import CatButton from "@/components/CatButton.vue";
export default {
  name: "App",
  components: {
    DisplaySelection,
    DogButton,
    CatButton,
  },
};
</script>

<style>
</style>
