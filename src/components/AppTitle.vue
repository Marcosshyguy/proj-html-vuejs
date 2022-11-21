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
    <hr />
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
.title-container {
  text-align: center;
  width: 70%;
  margin: 0 auto;

  hr {
    width: 35%;
    margin: 0 auto;
    margin-bottom: 1rem;
    border-color: $font-color1;
  }

  & > * {
    margin-bottom: 1rem;
  }

  & > *:last-child {
    margin-bottom: 0;
  }
}
</style>
