<script>
import { store } from "./store";
import AppHeader from "./components/AppHeader.vue";
import AppGridBandNews from "./components/AppGridBandNews.vue";
import AppFirstSection from "./components/AppFirstSection.vue";
import AppVideoThumbSectionVue from "./components/AppVideoThumbSection.vue";
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
      newsArray: [
        {
          title: "Tecnology and Music",
          text: "loremlorem lorem loem",
          image: "blog_music_techo-400x200.jpg",
        },
        {
          title: "Taking it back to the old school",
          text: "loremlorem lorem loem",
          image: "blog-post1-400x600.jpg",
        },
        {
          title: "While my guitar gently weeps",
          text: "loremlorem lorem loem loremlorem loloremlorem lo",
          image: "blog-post3-400x600.jpg",
        },
        {
          title: "It just sounds better",
          text: "loremlorem lorem loem loremlorem loloremlorem lo",
          image: "blog-post4-400x600.jpg",
        },
        {
          title: "Sharing the stage with legend",
          text: "loremlorem lorem loem loremlorem loloremlorem lo",
          image: "blog-post2-400x600.jpg",
        },
        {
          title: "Sharing the stage with legend",
          text: "loremlorem lorem loem loremlorem loloremlorem lo",
          image: "blog_flavor_rock-400x200.jpg",
        },
      ],
    };
  },
  components: {
    AppHeader,
    AppGridBandNews,
    AppFirstSection,
    AppVideoThumbSectionVue,
  },
  methods: {},
  props: {},
  computed: {},
  created() {},
};
</script>

<template>
  <!-- transparent header with a jumbo below it and an effect on the button on the right taht displays  a menu with several links -->
  <header>
    <AppHeader :linkList="linksArray" />
  </header>

  <!-- 1first of all a normal section, 2second a grid that shows latest newa some and an hover effect on them 
NEED TO ASK IF THE RED SECTION  MUST DO SOMETHIMG?, 3 another normal section with  bg images, fourth section that shows the most recent 
concert and for each date there is the possibilitY to view more details about plus the chanse to join that concert with a button,
NEED TO ASK IF THE RED BAR HAS TO SHOW MORE DATES-->
  <main>
    <AppFirstSection />
    <AppGridBandNews :newses="newsArray" />
    <AppVideoThumbSectionVue />
  </main>

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
