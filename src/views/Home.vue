<template>
  <before
    v-if="isBefore"
    :hours="hours"
    :minutes="minutes"
    :seconds="seconds"
  ></before>
  <during v-else-if="isDuring"></during>
  <after v-else></after>
</template>

<script>
import { start_time, end_time } from "../global.js";

const before = () => import("./../components/before.vue");
const during = () => import("./../components/during.vue");
const after = () => import("./../components/after.vue");

export default {
  name: "Home",
  data: () => ({
    hours: 0,
    minutes: 0,
    seconds: 0,
    polling: null,
  }),
  computed: {
    isBefore: function () {
      return +new Date() < start_time * 1000;
    },
    isDuring: function () {
      return +new Date() <= end_time * 1000;
    },
  },
  methods: {
    updateRemainingTime: function () {
      const remainingTimeInSeconds = Math.floor(start_time - new Date() / 1000);
      this.seconds = Math.floor(remainingTimeInSeconds % 60);
      this.minutes = Math.floor((remainingTimeInSeconds / 60) % 60);
      this.hours = Math.floor(remainingTimeInSeconds / 3600);
    },
  },
  mounted: function () {
    this.polling = setInterval(this.updateRemainingTime, 1);
  },
  unmounted: function () {
    clearInterval(this.polling);
  },
  components: { before, during, after },
};
</script>
