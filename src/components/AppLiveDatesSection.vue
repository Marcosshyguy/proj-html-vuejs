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
          <div class="event" @click="$emit('displayEvent', eventIndex)">
            <!-- ricordarsi di toglieree span -->
            <p>
              <span v-if="!event.status">+</span>
              <span v-else :class="event.status ? 'show' : ''">-</span>

              {{ event.when }} {{ event.what }} {{ event.where }}
            </p>
          </div>
          <div class="event-details" v-if="event.status">
            <div>
              <img
                src="../assets/images/fss-demo-main-400x300.jpg"
                alt="event location"
              />
            </div>
            <div class="details">
              <h4>{{ event.what }}</h4>
              <p>
                Lorem ipsum, dolor sit amet consectetur adipisicing elit.
                Deleniti voluptatem enim voluptas, praesentium dolores ut
                consectetur voluptatibus dolorum nulla necessitatibus vel quia
                illum, officiis sit odit nesciunt fugit amet quis.
              </p>
              <button @click="$emit('booking', eventIndex)">
                <span v-if="event.booking === 'notBooked'">Book now!</span
                ><span v-else>Cancel</span>
              </button>
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
        cursor: pointer;

        p {
          color: $secondary-color1;
          text-transform: uppercase;
          font-family: "Montserrat", sans-serif;
          font-size: 1rem;
        }

        span {
          font-size: 1.5rem;
          color: white;
          display: inline-block;
          width: 1.5rem;
          height: 1.5rem;
          line-height: 1.5rem;
          vertical-align: middle;
          text-align: center;
          margin-right: 1rem;

          &.show {
            background-color: $secondary-color1;
          }
        }
      }

      .event-details {
        background-color: $main-bg2;
        padding: 1rem;
        display: flex;
        // height: 200px;

        div {
          margin-right: 3em;

          img {
            object-fit: cover;
            width: 100%;
            height: 100%;
          }
        }

        .details {
          display: flex;
          flex-direction: column;
          align-items: flex-start;
          justify-content: space-between;

          h4 {
            font-weight: normal;
            letter-spacing: 0.1rem;
            margin-bottom: 0.5rem;
          }

          p {
            line-height: 1.3rem;
          }

          button {
            @include btn;
            background-color: $secondary-color1;
            border: none;
            margin-top: 1rem;
            padding: 0.5rem 1em;

            &:active {
              opacity: 50%;
            }
          }
        }
      }
    }
  }
}
</style>
