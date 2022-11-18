<script>
import { store } from "../store";

export default {
  data() {
    return {
      store,
      openedMenu: false,
    };
  },
  methods: {
    changeMenuStatus() {
      this.openedMenu = !this.openedMenu;
    },
  },
  props: {
    // linkList: Object,
  },
  computed: {},
  created() {},
};
</script>

<template>
  <div class="header-container">
    <!-- fixed navbar -->
    <div class="header-navbar">
      <div>
        <img src="../assets/images/logo_footer.png" alt="avda logo" />
      </div>
      <!-- humburger menu icon -->
      <span v-if="!openedMenu"
        ><i class="fa-solid fa-bars" @click="changeMenuStatus"></i
      ></span>
      <span v-else
        ><i class="fa-solid fa-xmark" @click="changeMenuStatus"></i
      ></span>
    </div>
    <!-- jumbotron -->
    <div class="jumbotron">
      <img src="../assets/images/home_slider.jpg" alt="" />
      <div class="jumbo-title">
        <h1>Untold Stories</h1>
        <p><em>There is an untold story behind every favourite song</em></p>
        <div class="mgt-2">
          <button>latest album</button>
          <button>live dates</button>
        </div>
      </div>
      <!-- menu list that is activated by the humburger menu icon in the header -->
      <div class="jumbo-menu" v-if="openedMenu">
        <ul>
          <li v-for="(link, indexLink) in store.linksArray" :key="indexLink">
            {{ link.name }}
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;
@use "../style/partials/mixins" as *;
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
    top: 5px;
    left: 0;

    i {
      cursor: pointer;
      // debug
      &:hover {
        // debug
        color: grey;
      }
    }
  }

  .jumbotron {
    height: 700px;
    position: relative;

    img {
      object-fit: fill;
      object-position: top;
      height: 100%;
    }
    .jumbo-title {
      width: 100%;
      text-align: center;
      color: white;

      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      z-index: 1;

      button {
        @include btn;
        margin-right: 1em;
        transition: 1s all;

        &:hover {
          background-color: $secondary-color1;
          border: none;
        }
      }
    }

    .jumbo-menu {
      width: 100%;
      height: 100%;
      background-color: $secondary-color1;
      color: white;

      position: absolute;
      z-index: 2;
      top: 0;
      left: 0;

      ul {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);

        li {
          font-family: "Montserrat", sans-serif;
          margin-bottom: 2rem;
          text-align: center;
        }
      }
    }
  }
}
</style>
