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
  props: {},
  computed: {},
  created() {},
};
</script>

<template>
  <div class="thumb">
    <div>
      <p>
        <em
          >&quot;I just listened to it and said to myself, &quot;Man I really
          love this album&quot;. Still, today, it just sounds so fresh. It
          sounds full of ideas. These guys knew what they were doing. They're
          good. And they're iventive. I haven't heard anything this year that's
          as inventive. I don't really expect to&quot;.</em
        >
      </p>
      <img src="../assets/images/band_interview_play_icon.png" alt="" />
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;
@use "../style/partials/mixins" as *;

.thumb {
  height: 800px;
  width: 100%;
  position: relative;
  background-color: aqua;
  background-image: url("../assets/images/home-testimonial-parallax.jpg");
  background-position: bottom;
  background-size: 2000px 700px;
  background-repeat: repeat-y;
  transition: all 2s;

  &:hover {
    background-position: top;
  }
  div {
    @include center-positioning;
    text-align: center;

    p {
      @include aforism;
    }

    img {
      width: 7%;
      margin-top: 2em;
      cursor: pointer;

      &:hover {
        opacity: 90%;
      }

      &:active {
        opacity: 0;
      }
    }
  }
}
</style>
