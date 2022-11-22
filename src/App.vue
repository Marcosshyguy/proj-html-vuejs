<script>
import { store } from "./store";
import AppHeader from "./components/AppHeader.vue";
import AppGridBandNews from "./components/AppGridBandNews.vue";
import AppFirstSection from "./components/AppFirstSection.vue";
import AppVideoThumbSectionVue from "./components/AppVideoThumbSection.vue";
import AppLiveDatesSection from "./components/AppLiveDatesSection.vue";
import AppFooter from "./components/AppFooter.vue";
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
          title: "Tecnology and music",
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
          text: "loremlorem lorem loem loremlorem loloremlorem lorem lore",
          image: "blog-post2-400x600.jpg",
        },
        {
          title: "Sharing the stage with legend",
          text: "loremlorem lorem loem loremlorem loloremlorem lo",
          image: "blog_flavor_rock-400x200.jpg",
        },
      ],
      liveDatesArray: [
        {
          when: "17/08/2020",
          where: "Analakia, Georgia",
          what: "Gem Festival 2020",
          status: false,
          booking: "notBooked",
        },
        {
          when: "24/9/2020",
          where: "Dominical Republic",
          what: "Groovefest",
          status: false,
          booking: "notBooked",
        },
        {
          when: "31/10/2020",
          where: "Marrakech, Morocco",
          what: "Oasis Festival 2020",
          status: false,
          booking: "notBooked",
        },
        {
          when: "07/11/2020",
          where: "- Essauria, Morocco",
          what: "Moga Festival",
          status: false,
          booking: "notBooked",
        },
        {
          when: "10/12/2020",
          where: "- Uvita, Costa Rica",
          what: "Envision Festival ",
          status: false,
          booking: "notBooked",
        },
      ],
      currentListPosition: 0,
      currentLinkPosition: 0,
    };
  },
  components: {
    AppHeader,
    AppGridBandNews,
    AppFirstSection,
    AppVideoThumbSectionVue,
    AppFooter,
    AppLiveDatesSection,
  },
  // use this methods to manage the list status according the emit button position
  // $emit from AppLiveDatesSection
  methods: {
    showEvents(index) {
      this.currentListPosition = index;
      let currentlistItem = this.liveDatesArray[this.currentListPosition];
      currentlistItem.status = !currentlistItem.status;
    },
    // use this methods to manage the booking status according the emit button position
    // $emit from AppLiveDatesSection
    bookEvents(index) {
      this.currentListPosition = index;
      let reservation = this.liveDatesArray[this.currentListPosition];
      if (reservation.booking === "notBooked") {
        reservation.booking = "booked";
      } else {
        reservation.booking = "notBooked";
      }
    },
    // this methods manage the position of the selected link of the footer and the header
    // $emit from AppHedaer App Footer
    changeLink(index) {
      this.linksArray[this.currentLinkPosition].status = false;
      this.currentLinkPosition = index;
      this.linksArray[this.currentLinkPosition].status = true;
    },
    // scrollTo(){
    //   scrollTo
    // }

    // }
  },
  props: {},
  computed: {},
  created() {},
};
</script>

<template>
  <!-- transparent header with a jumbo below it and an effect on the button on the right taht displays  a menu with several links -->
  <header>
    <AppHeader
      :linkList="linksArray"
      @selectionHedaer="changeLink"
      id="header"
    />
  </header>

  <!-- 1first of all a normal section, 2second a grid that shows latest newa some and an hover effect on them 
NEED TO ASK IF THE RED SECTION  MUST DO SOMETHIMG?, 3 another normal section with  bg images, fourth section that shows the most recent 
concert and for each date there is the possibilitY to view more details about plus the chanse to join that concert with a button,
NEED TO ASK IF THE RED BAR HAS TO SHOW MORE DATES-->
  <main>
    <AppFirstSection />
    <AppGridBandNews :newses="newsArray" />
    <AppVideoThumbSectionVue />
    <AppLiveDatesSection
      :eventsList="liveDatesArray"
      @displayEvent="showEvents"
      @booking="bookEvents"
    />
  </main>

  <!-- it seems a normal footer but with the same links of the header -->
  <footer>
    <AppFooter :linkList="linksArray" @selectionFooter="changeLink" />
    <a href="#header" class="scroll-up"
      ><i class="fa-solid fa-chevron-up"></i
    ></a>
  </footer>
</template>

<style lang="scss">
@use "./style/general.scss" as *;
@use "./style/partials/variables" as *;

header,
main,
footer {
  width: 100%;
  max-width: 2000px;
}

footer {
  position: relative;

  .scroll-up {
    display: inline-block;
    height: 2.3rem;
    width: 2.3rem;
    background-color: $main-bg2;
    line-height: 2.3rem;
    text-align: center;
    margin-right: 1rem;

    position: absolute;
    bottom: 3px;
    left: 80%;
  }
}
</style>
