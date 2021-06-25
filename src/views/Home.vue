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
    currentTime: null,
    hours: 0,
    minutes: 0,
    seconds: 0,
    polling: null,
  }),
  computed: {
    isBefore: function () {
      return this.currentTime <= start_time * 1000;
    },
    isDuring: function () {
      return this.currentTime <= end_time * 1000;
    },
  },
  methods: {
    updateRemainingTime: function () {
      this.currentTime = +new Date();
      const remainingTimeInSeconds = Math.floor(start_time - new Date() / 1000);
      this.seconds = Math.floor(remainingTimeInSeconds % 60);
      this.minutes = Math.floor((remainingTimeInSeconds / 60) % 60);
      this.hours = Math.floor(remainingTimeInSeconds / 3600);
    },
  },
  mounted: function () {
    this.currentTime = +new Date();
    this.polling = setInterval(this.updateRemainingTime, 1);
  },
  unmounted: function () {
    clearInterval(this.polling);
  },
  components: { before, during, after },
};
</script>
