<template>
  <v-layout column justify-center align-center class="mt-4 pt-2">
    <v-card-actions class="justify-center">
      <img src="@/photos/coder.png" class="rounded float-left" />
      <img src="@/photos/logo.png" class="rounded" id="logo" />
      <img src="@/photos/designer.png" class="rounded float-right" />
    </v-card-actions>

    <h1 class="blue--text font-weight-bold">Ahmed Cvrčak</h1>
    <h1> Full Stack Developer</h1>
  <v-flex xs12 sm6 md4 lg4 xl4>
      <v-card flat color="transparent" max-width="500">
        <v-card-title primary-title>
          <div>
            <h3 class="headline mb-0">
              <span>About</span>
              <span class="blue--text"> Me</span>
            </h3>
            <div>
              <p>
                Hello! I’m      <span class="blue--text">Ahmed Cvrčak</span> . I'm a Full Stack Junior Developer who
                is passionate about
                <span
                  class="blue--text font-weight-bold"
                >Vue.Js</span> and  <span
                  class="blue--text font-weight-bold"
                >Node.Js</span>, building great user experiences,
                fighting for simplicity over complexity and constantly learning.
                When I'm not coding or making videos, you'll find me on sports court.
              </p>
            </div>
          </div>
        </v-card-title>
  

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
      </v-card>
    </v-flex>

  </v-layout>
</template>

<script>
import { VueTyper } from "vue-typer";
import VueCompareImage from "vue-compare-image";

export default {
  metaInfo: {
    title: "Home",
    titleTemplate: "%s ← CA DEV",
    meta: [
      { name: "viewport", content: "width=device-width, initial-scale=1" },
      { name: "description", content: "Ahmed Cvrčak's Portfolio" },
      { charset: "utf-8" },
      { property: "og:title", content: "Ahmed Cvrčak" },
      { property: "og:site_name", content: "Ahmed Cvrčak" },
      { property: "og:type", content: "website" },
      { property: "og:url", content: "https://cadev.com" },
      {
        property: "og:image",
        content: "https://i.imgur.com/Dcz2PGx.jpg",
      },
      { property: "og:description", content: "Ahmed Cvrčak's Portfolio" },
    ],
  },
  components: {
    "vue-typer": VueTyper,
    VueCompareImage,
  },
  data() {
    return {
      icons: [
        {
          href: "https://github.com/MrGrigoryAlexandrovich",
          icon: "fab fa-github",
        },
        {
          href: "https://www.linkedin.com/in/ahmed-cvr%C4%8Dak-1a68a6201/",
          icon: "fab fa-linkedin-in",
        },
        {
          href: "https://web.facebook.com/cvrcak.ahmed/",
          icon: "fab fa-facebook-f",
        },
        {
          href: "https://www.instagram.com/_mr.assertive_/",
          icon: "fab fa-instagram",
        },
      ],
      text1: [
        "Full Stack Junior Developer",
        "Front-End Developer",
        "Back-End Developer",
        "Web Developer",
        "Web Designer",
      ],
      sliderLine: 0,
      hSize: 0,
      sliderPosition: 0.5,
    };
  },
};
</script>
<style scoped>
.divider-custom {
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.divider-custom .divider-custom-line {
  width: 100%;
  max-width: 7rem;
  height: 0.25rem;
  background-color: #2c3e50;
  border-radius: 1rem;
  border-color: #2c3e50;
}
.divider-custom .divider-custom-icon {
  color: #2c3e50;
  font-size: 2rem;
}
.divider-custom.divider-light .divider-custom-line {
  background-color: royalblue;
}
.divider-custom.divider-light .divider-custom-icon {
  color: royalblue;
}
.masthead {
  padding: 1rem;
}
.masthead .masthead-heading {
  font-size: 2.75rem;
  line-height: 2.75rem;
  text-align: center;
}
.masthead .masthead-subheading {
  font-size: 1.25rem;
}
.masthead .masthead-avatar {
  width: 5rem;
}
.flex-column {
  flex-direction: column !important;
}
@keyframes rocking {
  0%,
  100% {
    transform: rotateZ(-10deg);
  }
  50% {
    transform: rotateZ(10deg);
  }
}

#logo {
  height: 35%;
  width: 35%;
  margin-right: 60px;
  margin-left: 60px;
}
.float-left {
  height: 25%;
  width: 25%;
  margin-left: 100px;
}
.float-right {
  height: 25%;
  width: 25%;
  margin-right: 100px;
}
.vue-typer {
  font-family: Arial, "Helvetica Neue", Helvetica, sans-serif;
}
.vue-typer .custom.char.typed {
color:royalblue;
}
.vue-typer .custom.char.selected {
  color: grey;
}

.vue-typer .custom.caret {
  animation: rocking 1s ease-in-out 0s infinite;
}
.vue-typer .custom.caret.typing {
  background-color: green;
}
.vue-typer .custom.caret.selecting {
  display: inline-block;
  background-color: #e91e63;
}


@media only screen and (max-width: 600px) {
#logo {
  height: 35%;
  width: 35%;
  margin-right: 15px;
  margin-left: 30px;
}
.float-left {
  height: 30%;
  width: 30%;
}
.float-right {
  height: 30%;
  width: 30%;
}
}

</style>

