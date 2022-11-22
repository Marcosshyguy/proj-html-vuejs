<script>
import { store } from "../store";
import AppTitle from "./AppTitle.vue";
export default {
  data() {
    return {
      store,
      titleSection: "Latest Band News",
    };
  },
  components: { AppTitle },
  methods: {
    getImgPath(img) {
      return new URL(`../assets/images/${img}`, import.meta.url).href;
    },
  },
  props: {
    newses: Array,
  },
  computed: {},
  created() {},
};
</script>

<template>
  <div class="wrapper">
    <div class="main-container">
      <AppTitle :title="titleSection" />
      <!-- grid version -->
      <div class="grid">
        <div
          class="card-news"
          v-for="(news, indexNews) in newses"
          :key="indexNews"
        >
          <div class="image">
            <p>{{ news.title }}</p>
          </div>
          <div class="description">
            <h5>{{ news.title }}</h5>
            <p>{{ news.text }}</p>
          </div>
        </div>
      </div>
      <!-- flexbox version -->
      <!-- <div class="grid">
        <div class="grid-left-side">
          <div class="card">
            <img src="../assets/images/blog_music_techo-400x200.jpg" alt="" />
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
      </div> -->
    </div>
  </div>
  <div class="show-more">
    <a>View all Latest Dates</a>
  </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;
@use "../style/partials/mixins" as *;
// grid methods
.wrapper {
  background-color: $main-bg1;
  position: relative;
  .grid {
    height: 90vh;
    margin-top: 3em;
    display: grid;
    // set how many colums and row i want
    grid-template-rows: repeat(4, 1fr);
    grid-template-columns: repeat(3, 1fr);
    grid-gap: 1em;

    // card settings
    .card-news {
      overflow: hidden;

      &:nth-child(1),
      &:nth-child(6) {
        grid-row: span 1;
        grid-column: span 2;
      }
      &:nth-child(2),
      &:nth-child(3),
      &:nth-child(4),
      &:nth-child(5) {
        grid-row: span 2;
        grid-column: span 1;
      }
      // card backgrounds
      &:nth-child(4) {
        .image {
          background-image: url("../assets/images/blog-post4-600x900.jpg");
        }
      }

      &:nth-child(1) {
        .image {
          background-image: url("../assets/images/blog_music_techo-400x200.jpg");
        }
      }

      &:nth-child(2) {
        .image {
          background-image: url("../assets/images/blog-post1-400x600.jpg");
        }
      }

      &:nth-child(3) {
        .image {
          background-image: url("../assets/images/blog-post3-400x600.jpg");
        }
      }

      &:nth-child(5) {
        .image {
          background-image: url("../assets/images/blog-post2-400x600.jpg");
        }
      }

      &:nth-child(6) {
        .image {
          background-image: url("../assets/images/blog_flavor_rock-400x200.jpg");
        }
      }

      & {
        .image {
          height: 65%;
          background-size: cover;
          background-position: center;
          transition: all 2s;
          display: flex;
          justify-content: center;
          align-items: center;
          position: relative;
          &::before {
            content: "";
            display: block;
            background-color: $secondary-color1;
            opacity: 0;
            position: absolute;
            top: 0;
            right: 0;
            left: 0;
            bottom: 0;
            transition: opacity 1.5s;
          }

          p {
            color: white;
            text-align: center;
            letter-spacing: 1px;
            font-family: "Montserrat", sans-serif;
            font-size: 1rem;
            opacity: 0;
            z-index: 1;
            transition: opacity 2s;
          }
        }

        .description {
          height: 35%;
          padding: 0.4rem 0.6rem;
          background-color: $main-bg2;
          transition: all 1s;

          h5 {
            color: $secondary-color1;
            margin-bottom: 0.2rem;
          }

          p {
            line-height: 1.2rem;
          }
        }

        &:nth-child(2),
        &:nth-child(3),
        &:nth-child(4),
        &:nth-child(5) {
          .image {
            height: 80%;
          }
          .description {
            height: 20%;
          }
        }
      }
      // hover that scroll down the description section
      &:hover .description {
        height: 0%;
      }

      &:hover .image {
        height: 100%;
      }

      &:hover .image::before {
        opacity: 0.5;
      }

      &:hover .image p {
        opacity: 1;
      }
    }
  }
}
// large button at the end of the section
.show-more {
  @include btnLarge;

  &:hover {
    @include btnLargeHover;
  }
}
</style>
