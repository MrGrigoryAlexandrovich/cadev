<template>
  <v-container grid-list-xl>
            <v-flex xs12 sm12 md12 lg12 xl12>
        <h1 class="pl-4">
          <span class="blue--text">My Projects</span>
        </h1>
      </v-flex>
    <h2 style="text-align:center">Click and Open</h2>
    <v-layout row justify-center align-center wrap class="mt-4 pt-5">
              <v-flex xs12 sm12 md12 lg12 xl12>
        <h2 class="pl-4">
          <span class="blue--text">Graphic</span>
        </h2>
      </v-flex>
          <v-layout row justify-center align-center wrap class="mt-4 pt-2">
      <v-dialog
        v-model="image.dialog"
        lazy
        max-width="800"
        v-for="image in images"
        :key="image.title"
      >
        <template v-slot:activator="{ on }">
          <v-flex xs12 sm6 md4 lg4 xl4 v-on="on">
            <v-card hover flat color="transparent">
              <v-img
                :src="image.poster"
                height="230"
                :alt="image.title"
                lazy-src="https://cdn.dribbble.com/users/503653/screenshots/3143656/fluid-loader.gif"
              ></v-img>
              <v-card-title primary-title class="justify-center">{{image.title}}</v-card-title>
            </v-card>
          </v-flex>
        </template>
        <v-card v-if="image.dialog">
          <v-img :src="image.poster"></v-img>
        </v-card>
      </v-dialog>
    </v-layout>

          <v-flex xs12 sm12 md12 lg12 xl12>
        <h2 class="pl-4">
          <span class="blue--text"> Web Development</span>
        </h2>
      </v-flex>
 <v-flex v-for="serv in services" :key="serv.src" xs6 sm4 md3 lg2 xl2>
        <v-card-title class="justify-center">
          <v-flex text-xs-center subheading font-weight-bold>{{
            serv.name
          }}</v-flex>
        </v-card-title>
        <v-card
          hover
          flat
          color="transparent"
          :href="serv.href"
          target="_blank"
        >
          <v-img
            :src="serv.src"
            :alt="serv.name + ' logo'"
            lazy-src="https://cdn.dribbble.com/users/503653/screenshots/3143656/fluid-loader.gif"
            height="100"
            width="160"
            aspect-ratio="2.75"
            contain
          >
          </v-img>
        </v-card>
      </v-flex>
    </v-layout>
   <br><br>
            <v-card-actions class="justify-center">
      <v-btn
        v-for="icon in icons"
        :key="icon.icon"
        small
        fab
        dark
        outline
        color="blue"
        :href="icon.href"
        target="_blank"
      >
        <v-icon dark>{{ icon.icon }}</v-icon>
      </v-btn>
    </v-card-actions>
  </v-container>
</template>

<script>
export default {
  metaInfo: {
    title: "Services",
    titleTemplate: "%s ← CA DEV",
    meta: [
      { name: "viewport", content: "width=device-width, initial-scale=1" },
      {
        name: "description",
        content:
          "Ahmed Cvrčak's Services Web Development Video Editing Graphic Design Front-End Advetising",
      },
      { charset: "utf-8" },
      { property: "og:title", content: "Ahmed' Cvrčak" },
      { property: "og:site_name", content: "Ahmed' Cvrčak" },
      { property: "og:type", content: "website" },
      { property: "og:url", content: "https://cadev" },
      {
        property: "og:image",
        content: "https://i.imgur.com/Dcz2PGx.jpg",
      },
      {
        property: "og:description",
        content:
          "Ahmed Cvrčak's Services Web Development Video Editing Graphic Design Front-End Advetising",
      },
    ],
  },
  data() {
    return {
      technologies: [
        {
          name: "HTML",
          src: "https://i.imgur.com/575bMEA.png",
          href: "https://www.w3schools.com/html/",
        },
        {
          name: "CSS",
          src: "https://i.imgur.com/a7ZjXKd.png",
          href: "https://www.w3schools.com/css/",
        },
      ],
      services: [
        {
          src: "https://i.imgur.com/a9xdOTX.png",
          name: "URL Shortener",
          href: "https://easy-sh.netlify.app/"
        },
        {
          src: "https://i.imgur.com/wzz2Kkf.png",
          name: "CA DEV",
          href: "https://cadev.netlify.app/"
        },
      ],
       images: [
        {
          title: "CA DEV Logo",
          poster: "https://i.imgur.com/uLr0UsE.png"
        },
        {
          title: "KM STIL Visit Card",
          poster: "https://i.imgur.com/RkjO9i3.jpg"
        },
      ],
                        icons: [
        {
          href: "https://web.facebook.com/cvrcak.ahmed/",
          icon: "fab fa-facebook-f",
        },
        {
          href: "https://www.instagram.com/_mr.assertive_/",
          icon: "fab fa-instagram",
        },
                {
          href: "https://github.com/MrGrigoryAlexandrovich",
          icon: "fab fa-github",
        },
        {
          href: "https://www.linkedin.com/in/ahmed-cvr%C4%8Dak-1a68a6201/",
          icon: "fab fa-linkedin-in",
        },
      ],
    };
  },
};
</script>
<style scooped>
.v-img--reveal {
  opacity: 0.3;
}
</style>