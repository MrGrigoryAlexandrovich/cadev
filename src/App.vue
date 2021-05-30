<template>
  <div id="app">
  <v-app :dark="goDark">
    <v-content>
      <v-container align-center>
        <TheHeader :goDark="goDark" @changeTheme="updateTheme($event)"/>
        <transition
          name="router-animation"
          mode="out-in"
          enter-active-class="animated fadeIn fast"
          leave-active-class="animated fadeOut faster"
        >
          <router-view></router-view>
        </transition>
      </v-container>
    </v-content>
  </v-app>
  </div>
</template>

<script>
import TheHeader from "./components/TheHeader";

export default {
  name: "App",
  metaInfo: {
    title: "Home",
    titleTemplate: "%s ← CA DEV",
    meta: [
      { name: "viewport", content: "width=device-width, initial-scale=1" },
      { name: "description", content: "Ahmed Cvrčakc's Portfolio" },
      { charset: "utf-8" },
      { property: "og:title", content: "Ahmed' Cvrčak" },
      { property: "og:site_name", content: "Ahmed' Cvrčak" },
      { property: "og:type", content: "website" },
      { property: "og:url", content: "https://cadev" },
      {
        property: "og:image",
        content: "https://i.imgur.com/Dcz2PGx.jpg"
      },
      { property: "og:description", content: "Ahmed Cvrčak's Portfolio" }
    ]
  },
  components: {
    TheHeader,
  },
  data() {
    return { goDark: false };
  },
  methods: {
    updateTheme(updatedTheme) {
      this.goDark = !updatedTheme;
    }
  },
  mounted() {
    this.updateTheme()
  }
};
</script>

<style>
#app {
  margin:0px;
}
* {
  margin:0px;
}
body {
  margin:0px;
}
</style>

