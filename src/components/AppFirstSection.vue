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
  <div class="wrapper">
    <div class="main-container">
      <AppTitle :title="titleSection" />
    </div>
    <div class="red-bar">&nbsp</div>
  </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;
@use "../style/partials/mixins" as *;
.wrapper {
  background-color: $main-bg2;
  position: relative;
  .red-bar {
    height: 10px;
    width: 450px;
    background-color: $secondary-color1;
    position: absolute;
    top: 0;
    left: 50%;
    transform: translateX(-50%);
  }
}
</style>
