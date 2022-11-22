<script>
export default {
  data() {
    return {};
  },
  components: {},
  methods: {},
  props: { linkList: Array },
  computed: {},
  created() {},
};
</script>

<template>
  <!-- footer top -->
  <div class="footer-menu">
    <div>
      <img src="../assets/images/logo_footer.png" alt="avada-logo" />
    </div>
    <div>
      <ul>
        <li
          v-for="(link, index) in linkList"
          :key="index"
          :class="link.status ? 'selected' : ''"
          @click="$emit('selectionFooter', index)"
        >
          <a>{{ link.name }}</a>
        </li>
      </ul>
    </div>
  </div>
  <!-- footer bottom -->

  <div class="footer-credits">
    <p>
      &#169; Copyright 2012 - 2020 | AVADA THEME BY THEMEFUSIUN | ALL RIGHTS
      RESERVED | POWERED BY WORDPRESS
    </p>
    <div>
      <a href=""><i class="fa-brands fa-facebook-f"></i></a>
      <a href=""><i class="fa-brands fa-twitter"></i></a>
      <a href=""><i class="fa-brands fa-instagram"></i></a>
      <a href=""><i class="fa-brands fa-youtube"></i></a>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;
@use "../style/partials/mixins" as *;

.footer-menu {
  background-color: $main-bg2;
  width: 100%;
  height: $hedaer-height;
  padding: 0 2em;

  display: flex;
  justify-content: space-between;
  align-items: center;

  ul {
    display: flex;
    gap: 1.5em;

    li {
      color: $font-color1;
      cursor: pointer;

      &.selected {
        color: white;
      }

      &:hover {
        opacity: 75%;
      }
    }
  }
}
.footer-credits {
  color: $font-color1;
  background-color: $main-bg1;
  width: 100%;
  height: $footer-credits;
  padding: 0 2em;

  display: flex;
  justify-content: space-between;
  align-items: center;

  a {
    display: inline-block;
    height: 2.3rem;
    width: 2.3rem;
    background-color: $main-bg2;
    line-height: 2.3rem;
    text-align: center;
    margin-right: 1rem;

    &:hover {
      opacity: 75%;
    }

    &:last-child {
      margin-right: 0;
    }
  }
}
</style>
