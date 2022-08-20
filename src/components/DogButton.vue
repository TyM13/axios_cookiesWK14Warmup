<template>
  <div>
    <button @click="show_dog">Dog Image</button>
  </div>
</template>

<script>
import cookies from "vue-cookies";
import axios from "axios";

export default {
  mounted() {
    if (cookies.get(`selection`) === `dog`) {
      this.show_dog();
    }
  },

  methods: {
    show_dog() {
      axios
        .request({
          url: `https://dog.ceo/api/breeds/image/random`,
        })
        .then((response) => {
          this.$root.$emit(`new_display`, response[`data`][`message`]);
          cookies.set(`selection`, `dog`);
        })
        .catch((error) => {
          error;
        });
    },
  },
};
</script>

<style scoped>
</style>