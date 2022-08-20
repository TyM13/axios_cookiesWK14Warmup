<template>
  <div>
    <button @click="show_cat">cat img</button>
  </div>
</template>

<script>
import cookies from "vue-cookies";
import axios from "axios";
export default {
  mounted() {
    if (cookies.get(`selection`) === `cat`) {
      this.show_cat();
    }
  },

  methods: {
    show_cat() {
      axios
        .request({
          url: `https://aws.random.cat/meow`,
        })
        .then((response) => {
          this.$root.$emit(`new_display`, response[`data`][`file`]);
          cookies.set(`selection`, `cat`);
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