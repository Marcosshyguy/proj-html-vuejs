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
  <div class="footer-navbar">
    <div>
      <img src="../assets/images/logo_footer.png" alt="avada logo" />
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
  <div class="footer-credits"></div>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;
@use "../style/partials/mixins" as *;

.footer-navbar {
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
</style>
