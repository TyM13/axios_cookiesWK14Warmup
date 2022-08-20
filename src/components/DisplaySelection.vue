<template>
  <div v-if="url != undefined">
    <img :src="url" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      url: undefined,
    };
  },

  methods: {
    handle_display(image_url) {
      this.url = image_url;
    },
  },

  mounted() {
    this.$root.$on(`new_display`, this.handle_display);
  },
};
</script>

<style scoped>
</style>    