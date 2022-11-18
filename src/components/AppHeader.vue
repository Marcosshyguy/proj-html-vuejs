<script>
import { store } from "../store";

export default {
  data() {
    return {
      store,
    };
  },
  methods: {},
  props: {},
  computed: {},
  created() {},
};
</script>

<template>
  <div class="header-container">
    <div class="header-navbar">
      <div>
        <img src="../assets/images/logo_footer.png" alt="avda logo" />
      </div>

      <span><i class="fa-solid fa-bars"></i></span>
    </div>
    <div class="jumbotron">
      <img src="../assets/images/home_slider.jpg" alt="" />
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;

.header-container {
  width: 100%;
  position: relative;
  .header-navbar {
    width: 100%;
    height: $hedaer-height;
    padding: 0 1em;

    display: flex;
    justify-content: space-between;
    align-items: center;

    position: fixed;
    z-index: 999;
    top: 0;
    left: 0;
  }

  .jumbotron {
    height: 700px;

    img {
      object-fit: fill;
      object-position: top;
      height: 100%;
    }
  }
}
</style>
