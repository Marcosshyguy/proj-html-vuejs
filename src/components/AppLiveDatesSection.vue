<script>
import AppTitle from "./AppTitle.vue";
export default {
  data() {
    return { titleSection: "Live Dates" };
  },
  components: { AppTitle },
  methods: {},
  props: { eventsList: Array },
  computed: {},
  created() {},
};
</script>

<template>
  <div class="wrapper">
    <div class="main-container">
      <AppTitle :title="titleSection" />
      <div class="events-list">
        <div
          class="event-container"
          v-for="(event, eventIndex) in eventsList"
          :key="eventIndex"
        >
          <div class="event">
            <!-- ricordarsi di toglieree span -->
            <p>
              <span>+</span> {{ event.when }} {{ event.what }} {{ event.where }}
            </p>
          </div>
          <div class="event-details">
            <div>
              <img
                src="../assets/images/fss-demo-main-400x300.jpg"
                alt="demo"
              />
            </div>
            <div>
              <h5>sfesf</h5>
              <p>
                Lorem ipsum, dolor sit amet consectetur adipisicing elit.
                Deleniti voluptatem enim voluptas, praesentium dolores ut
                consectetur voluptatibus dolorum nulla necessitatibus vel quia
                illum, officiis sit odit nesciunt fugit amet quis.
              </p>
              <button>Book Now</button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;
@use "../style/partials/mixins" as *;
.wrapper {
  background-color: $main-bg1;

  .events-list {
    margin-top: 3rem;
    .event-container {
      margin-bottom: 0.8em;

      .event {
        padding: 1rem;
        background-color: $main-bg2;

        span {
          margin-right: 1rem;
          cursor: pointer;
        }
      }
    }
  }
}
</style>
