<script>
import { store } from "./store";
import AppHeader from "./components/AppHeader.vue";

export default {
  data() {
    return {
      store,
      linksArray: [
        {
          name: "Home",
          status: true,
        },
        {
          name: "Meet the band",
          status: false,
        },
        {
          name: "Lives Dates",
          status: false,
        },
        {
          name: "Albums",
          status: false,
        },
        {
          name: "Fans",
          status: false,
        },
      ],
    };
  },
  components: {
    AppHeader,
  },
  methods: {},
  props: {},
  computed: {},
  created() {},
};
</script>

<template>
  <!-- transparent header with a jubo below it and an effect on the button on the right taht displays  a menu with several links -->
  <header>
    <AppHeader />
  </header>

  <!-- 1first of all a normal section, 2second a grid that shows latest newa some and an hover effect on them 
NEED TO ASK IF THE RED SECTION  MUST DO SOMETHIMG?, 3 another normal section with  bg images, fourth section that shows the most recent 
concert and for each date there is the possibilitY to view more details about plus the chanse to join that concert with a button,
NEED TO ASK IF THE RED BAR HAS TO SHOW MORE DATES-->
  <main></main>

  <!-- it seems a normal footer but with the same links of the header -->
  <footer></footer>
</template>

<style lang="scss">
@use "./style/general.scss" as *;

header,
main,
footer {
  width: 100%;
  max-width: 2000px;
}
</style>
