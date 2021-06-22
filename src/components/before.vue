<template>
  <v-container class="pa-6" fluid fill-height>
    <v-row
      class="text-center"
      align-content="center"
      justify="center"
      align="center"
    >
      <v-col
        cols="12"
        class="text-h6 text-md-h5 yellow--text text--lighten-2 ma-2 pa-0"
      >
        Are you ready?
      </v-col>
      <v-col
        cols="12"
        class="
          text-h5 text-md-h4
          yellow--text
          text--lighten-2
          font-weight-bold
          ma-2
          pa-0
        "
      >
        Hey, are you ready for this?
      </v-col>
      <v-col
        cols="12"
        class="
          text-h4 text-md-h3
          yellow--text
          text--lighten-2
          font-weight-bold
          ma-2
          pa-0
        "
      >
        Are you hanging on the edge of your seat?
      </v-col>
      <v-col cols="12"> </v-col>

      <v-col>
        <v-img max-height="50" contain src="../assets/ribbon.png"></v-img>
      </v-col>

      <v-col cols="12"> </v-col>
      <v-col cols="12" class="text-h5 yellow--text text-md-h1"
        >{{ remainingTimeString }}
      </v-col>
      <v-col cols="12" class="text-h4 yellow--text text--lighten-2 text-md-h3">
        till your socks are
      </v-col>
      <v-col
        cols="12"
        class="text-h3 yellow--text text--lighten-2 text-md-h2 font-weight-bold"
      >
        rocked off!
      </v-col>
      <v-col cols="12" v-if="isBigScreen"> </v-col>
      <v-col cols="12"> </v-col>

      <v-col cols="12" class="pa-0"
        ><a
          class="link"
          href="https://www.instagram.com/tv/CQYvwXABLzH/?utm_medium=copy_link"
        >
          <v-btn
            class="text-button font-weight-medium yellow--text"
            color="#743282"
            elevation="4"
            large
          >
            Watch the Trailer
          </v-btn>
        </a>
      </v-col>
    </v-row>

    <v-row class="pt-4">
      <v-col cols="12" align-content="center" justify="center" align="center">
        <a class="link" href="https://www.instagram.com/eeyore_mari/">
          <v-icon class="footer-icons">mdi-instagram</v-icon>
        </a>
        <a class="link" href="https://www.twitch.tv/eeyore_ismy_sidekick">
          <v-icon class="footer-icons">mdi-twitch</v-icon>
        </a>
        <a class="link" href="https://twitter.com/eeyore_mari">
          <v-icon class="footer-icons">mdi-twitter</v-icon>
        </a>
        <a
          class="link"
          href="https://www.youtube.com/channel/UC3gdavq5axNUwf7N8410flA"
        >
          <v-icon class="footer-icons">mdi-youtube</v-icon>
        </a>
      </v-col>
    </v-row>
  </v-container>
</template>


<style>
.link {
  text-decoration: none;
}

.footer-icons {
  padding-right: 20px;
  padding-left: 20px;
}
</style>


<script>
export default {
  name: "before",
  props: { hours: Number, minutes: Number, seconds: Number },
  computed: {
    isBigScreen: function () {
      return this.$vuetify.breakpoint.mdAndUp;
    },
    remainingTimeString: function () {
      const hoursWord = this.hours === 1 ? "hour" : "hours";
      const minutesWord = this.minutes < 2 ? "minute" : "minutes";
      const secondsWord = this.seconds < 2 ? "second" : "seconds";
      if (this.hours > 0) {
        return `${this.hours} ${hoursWord}, ${this.minutes} ${minutesWord}, and ${this.seconds} ${secondsWord}`;
      }
      return `${this.minutes} ${minutesWord}, and ${this.seconds} ${secondsWord}`;
    },
  },
};
</script>