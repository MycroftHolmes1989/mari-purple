<template>
  <v-app>
    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<style>
.v-main {
  background: #441c55;
}
</style>

<script>
export default {
  name: "App",

  data: () => ({
    //
  }),
};
</script>
