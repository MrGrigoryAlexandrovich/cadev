<template>
  <v-container grid-list-xl>
    <v-layout row justify-center align-center wrap class="mt-4 pt-2">
      <v-flex xs12 sm12 md12 lg12 xl12>
        <h2 class="pl-4">
          <span class="blue--text"> Services</span>
        </h2>
      </v-flex>
      <v-flex
        v-for="service in services"
        :key="service.src"
        xs6
        sm3
        md3
        lg3
        xl3
      >
        <v-card
          hover
          flat
          color="transparent"
          :style="{ cursor: 'context-menu' }"
        >
          <v-card-title></v-card-title>
          <v-img
            :src="service.src"
            height="100"
            aspect-ratio="2.75"
            :alt="service.title"
            lazy-src="https://cdn.dribbble.com/users/503653/screenshots/3143656/fluid-loader.gif"
            contain
          ></v-img>
          <v-card-title class="justify-center">
            <v-flex text-xs-center subheading font-weight-bold>{{
              service.title
            }}</v-flex>
          </v-card-title>
        </v-card>
      </v-flex>
      <v-flex xs12 sm12 md12 lg12 xl12>
        <h2 class="pl-4">
          <span class="blue--text"> Technologies</span>
        </h2>
      </v-flex>

      <v-flex v-for="tech in technologies" :key="tech.src" xs6 sm4 md3 lg2 xl2>
        <v-card-title class="justify-center">
          <v-flex text-xs-center subheading font-weight-bold>{{
            tech.name
          }}</v-flex>
        </v-card-title>
        <v-card
          hover
          flat
          color="transparent"
          :href="tech.href"
          target="_blank"
        >
          <v-img
            :src="tech.src"
            :alt="tech.name + ' logo'"
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
        {
          name: "Javascript",
          src: "https://i.imgur.com/qkX6Zhe.png",
          href: "https://www.javascript.com/",
        },
        {
          name: "Vue.Js",
          src: "https://i.imgur.com/qn0EvPO.png",
          href: "https://vuejs.org/",
        },
        {
          name: "Node.Js",
          src: "https://i.imgur.com/QqEp8Ir.png",
          href: "https://nodejs.org/",
        },
        {
          name: "Nuxt.Js",
          src: "https://i.imgur.com/T0MD5IX.png",
          href: "https://nuxtjs.org/",
        },
        {
          name: "MySQL",
          src: "https://i.imgur.com/Wm2JeQD.png",
          href: "https://www.mysql.com/",
        },
        {
          name: "MongoDB",
          src: "https://i.imgur.com/5GlLlHY.png",
          href: "https://www.mongodb.com/",
        },
        {
          name: "Sequelize",
          src: "https://i.imgur.com/zykWBz9.png",
          href: "https://sequelize.org//",
        },
        {
          name: "GIT",
          src: "https://i.imgur.com/syLz8qM.png",
          href: "https://git-scm.com/",
        },
        {
          name: "GitHub",
          src: "https://i.imgur.com/eUBclVB.png",
          href: "https://github.com/",
        },
        {
          name: "Docker",
          src: "https://i.imgur.com/OQlssC7.png",
          href: "https://www.docker.com/",
        },
        {
          name: "Bootstrap",
          src: "https://i.imgur.com/BhCAUdV.png",
          href: "https://getbootstrap.com/",
        },
        {
          name: "Vuetify",
          src: "https://i.imgur.com/nelKeFz.png",
          href: "https://vuetifyjs.com/en/",
        },
        {
          name: "Photoshop",
          src: "https://i.imgur.com/DMPzorz.png",
          href: "https://www.photoshop.com/en",
        },
      ],
      services: [
        {
          src: "https://i.imgur.com/GvTt5GG.png",
          title: "Web Development",
        },
        {
          src: "https://i.imgur.com/g74mGuU.png",
          title: "Web Design",
        },

        {
          src: "https://i.imgur.com/wXLtLKy.png",
          title: "Video Editing",
        },
        {
          src: "https://i.imgur.com/BO8b8Rr.png",
          title: "Photo Editing",
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