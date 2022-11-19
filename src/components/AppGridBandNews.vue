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
  <div class="main-container">
    <div class="title-container">
      <h2>Latest Band News</h2>
      <!-- linea  -->
      <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Vero obcaecati
        ipsa Praesentium velit, nobis amet sit asperiores similique quo sequi
        ducimus.
      </p>
    </div>
    <div class="grid">
      <div class="grid-left-side">
        <div class="card">
          <img src="../assets/images/blog_music_techo-800x400.jpg" alt="" />
        </div>
        <div class="card-flex">
          <div class="card">
            <img src="../assets/images/blog-post3-600x900.jpg" alt="" />
          </div>
          <div class="card">
            <img src="../assets/images/blog-post4-400x600.jpg" alt="" />
          </div>
        </div>
        <div class="card">
          <img src="../assets/images/blog_flavor_rock-200x100.jpg" alt="" />
        </div>
      </div>
      <div class="grid-right-side">
        <div class="card">
          <img src="../assets/images/blog-post1-400x600.jpg" alt="" />
        </div>
        <div class="card">
          <img src="../assets/images/blog-post2-400x600.jpg" alt="" />
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;
@use "../style/partials/mixins" as *;
.grid {
  height: 90vh;
  width: 100%;
  display: flex;
  margin: 0 auto;
  gap: 1em;

  //   leftside
  .grid-left-side {
    height: 100%;
    width: 66%;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    gap: 1em;

    .card:first-child,
    .card:last-child {
      height: calc(100% / 4 - 1em);
      border: 1px solid black;
    }

    .card-flex {
      flex-grow: 1;
      border: 1px solid black;
      display: flex;
      gap: 1em;
      .card {
        width: calc(100% / 2);
        height: 100%;
        // img {
        //   width: 100%;
        //   height: 100%;
        //   object-fit: fill;
        // }
      }
    }
  }
  //   right-side
  .grid-right-side {
    border: 1px solid black;
    height: 100%;
    width: 33%;
    display: flex;
    flex-direction: column;
    gap: 1em;

    .card {
      height: calc(100% / 2);
      border: 1px solid black;
    }
  }
  img {
    width: 100%;
    height: 100%;
    object-fit: fill;
  }
}
</style>
