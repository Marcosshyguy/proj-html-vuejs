<script>
export default {
  data() {
    return {
      openedMenu: false,
      currentBtnPosition: 0,
      jumboButtons: [
        { status: true, name: "Latest Album" },
        {
          status: false,
          name: "Live Dates",
        },
      ],
    };
  },
  methods: {
    changeMenuStatus() {
      this.openedMenu = !this.openedMenu;
    },
    changeBtnStatus(index) {
      this.jumboButtons[this.currentBtnPosition].status = false;
      this.currentBtnPosition = index;
      this.jumboButtons[this.currentBtnPosition].status = true;
    },
  },
  props: {
    linkList: Array,
  },
  computed: {},
  created() {},
};
</script>
<!-- fix link status link -->
<template>
  <div class="header-container">
    <!-- fixed navbar -->
    <div class="header-navbar">
      <div>
        <img src="../assets/images/logo_footer.png" alt="avada logo" />
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
      <!-- <img src="../assets/images/home_slider.jpg" alt="home-slider" /> -->
      <div class="jumbo-title">
        <h1>Untold Stories</h1>
        <p><em>There is an untold story behind every favourite song</em></p>
        <div class="mgt-2">
          <button
            v-for="(btn, btnIndex) in jumboButtons"
            :key="btnIndex"
            :class="btn.status ? 'active' : ''"
            @click="changeBtnStatus(btnIndex)"
          >
            {{ btn.name }}
          </button>
        </div>
      </div>

      <!-- menu list that is activated by the humburger menu icon in the header -->
      <div class="jumbo-menu" v-if="openedMenu" @click="changeMenuStatus">
        <ul>
          <li
            v-for="(link, index) in linkList"
            :key="index"
            :class="link.status ? 'selected' : ''"
            @click="$emit('selectionHedaer', index)"
          >
            <a @click="$emit('selection', index)">{{ link.name }}</a>
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

  &:hover .jumbotron {
    background-position: center;
  }
  .header-navbar {
    width: 100%;
    height: $hedaer-height;
    padding: 0 2em;

    display: flex;
    justify-content: space-between;
    align-items: center;

    position: absolute;
    z-index: 999;
    top: 5px;
    left: 0;
    i {
      cursor: pointer;
      color: $font-color1;
      font-size: 1.3rem;
      &:hover {
        color: grey;
      }
    }
  }

  .jumbotron {
    height: 800px;
    position: relative;
    background-image: url(../assets/images/home_slider.jpg);
    background-size: cover;
    background-position: bottom;
    transition: all 2s;

    p {
      @include aforism;
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
        transition: 300ms all ease-in-out;

        &.active {
          background-color: $secondary-color1;
          border: none;
        }

        &:hover {
          background-color: white;
          color: black;
          border: 1px solid black;
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
          font-size: 1.5rem;
          color: $font-color1;
          margin-bottom: 2rem;
          text-align: center;
          cursor: pointer;

          &.selected {
            color: white;
          }

          &:hover {
            transform: scale(1.1);
          }
        }
      }
    }
  }
}
</style>
