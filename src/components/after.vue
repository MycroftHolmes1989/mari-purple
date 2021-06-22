<template>
  <v-container fill-height class="pa-4">
    <v-row
      class="text-center font-"
      align-content="center"
      justify="center"
      align="center"
    >
      <v-col cols="12" class="pa-0">
        <v-icon color="yellow" size="200%">mdi-sleep</v-icon>
      </v-col>

      <v-col cols="12"> </v-col>
      <v-col
        cols="12"
        class="text-h6 text-md-h5 yellow--text text--lighten-2 ma-2 pa-0"
      >
        It's over.
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
        Go get some sleep now.
      </v-col>

      <v-col cols="12"> </v-col>

      <v-col>
        <v-img max-height="50" contain src="../assets/ribbon.png"></v-img>
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