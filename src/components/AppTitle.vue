<script>
import { store } from "../store";

export default {
  data() {
    return {
      store,
    };
  },
  components: {},
  methods: {},
  props: {
    title: String,
  },
  computed: {},
  created() {},
};
</script>

<template>
  <div class="title-container">
    <h2>{{ title }}</h2>
    <p>
      Lorem ipsum, dolor sit amet consectetur adipisicing elit. Vero obcaecati
      ipsa Praesentium velit, nobis amet sit asperiores similique quo sequi
      ducimus.
    </p>
  </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;
@use "../style/partials/mixins" as *;
</style>
