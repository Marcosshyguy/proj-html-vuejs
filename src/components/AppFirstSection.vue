<script>
import { store } from "../store";
import AppTitle from "./AppTitle.vue";
export default {
  data() {
    return {
      store,
      titleSection: "Music Is Life",
    };
  },
  components: {
    AppTitle,
  },
  methods: {},
  props: {},
  computed: {},
  created() {},
};
</script>

<template>
  <div class="main-container">
    <AppTitle :title="titleSection" />
  </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;
@use "../style/partials/mixins" as *;
</style>
