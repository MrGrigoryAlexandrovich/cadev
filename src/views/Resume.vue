<template>
  <v-layout row justify-center align-center wrap class="mt-4 pt-2">
    <v-flex xs12 sm12 md5 lg6 xl6 class="mt-4 pt-4">
      <h2 class="mb-4 pl-4 pt-2">Education</h2>
      <v-card-text class="py-0">
        <v-timeline align-top dense>

          <v-timeline-item color="blue" small>
            <v-layout pt-3>
              <v-flex xs4>
                <div class="caption font-weight-bold blue--text">SEP 2012 -</div>
                <div class="caption font-weight-bold blue--text">MAY 2016</div>
              </v-flex>
              <v-flex class="pl-2">
                <strong>HIGH SCHOOL</strong>
                <div class="caption mb-2">Gimnazija Edhem Mulabdić Maglaj</div>
              </v-flex>
            </v-layout>
          </v-timeline-item>

                  <v-timeline-item color="blue" small>
            <v-layout pt-3>
              <v-flex xs4>
                <div class="caption font-weight-bold blue--text">OCT 2019 -</div>
                <div class="caption font-weight-bold blue--text">AUGUST 2020</div>
              </v-flex>
              <v-flex class="pl-2">
                <strong>Full Stack Web Development Course</strong>
                <div class="caption mb-2">SPARK - nSoft Maglaj</div>
              </v-flex>
            </v-layout>
          </v-timeline-item>

          <v-timeline-item color="blue" small>
            <v-layout pt-3>
              <v-flex xs4>
                <div class="caption font-weight-bold blue--text">OCT 2016 -</div>
                <div class="caption font-weight-bold blue--text">SEP 2020</div>
              </v-flex>
              <v-flex class="pl-2">
                <strong>Computing science and informatics</strong>
                <div class="caption mb-2">VPTŠ Doboj</div>
              </v-flex>
            </v-layout>
          </v-timeline-item>
        </v-timeline>
      </v-card-text>
    </v-flex>
    <v-flex xs12 sm12 md4 lg6 xl6 class="mt-4 pt-2">
      <h2 class="mb-4 pl-4">Experience</h2>
      <v-card-text class="py-0">
        <v-timeline align-top dense>
          <v-timeline-item color="blue" small>
            <v-layout pt-3>
              <v-flex xs4>
                <div class="caption font-weight-bold blue--text">AUG 2019 -</div>
                <div class="caption font-weight-bold blue--text">MAR 2020</div>
              </v-flex>
              <v-flex class="pl-2">
                <strong>Recepcionist and personal trainer</strong>
                <div class="caption mb-2">Gym Xtreme - Fitness center, Novi Šeher - Maglaj</div>
              </v-flex>
            </v-layout>
          </v-timeline-item>
          <v-timeline-item color="blue" small>
            <v-layout pt-3>
              <v-flex xs4>
                <div class="caption font-weight-bold blue--text">JUN 2020 -</div>
                <div class="caption font-weight-bold blue--text">SEP 2020</div>
              </v-flex>
              <v-flex class="pl-2">
                <strong>nSoft Devhive - Programmer practice</strong>
                <div class="caption mb-2">nSoft Maglaj</div>
              </v-flex>
            </v-layout>
          </v-timeline-item>

               <v-timeline-item color="blue" small>
            <v-layout pt-3>
              <v-flex xs4>
                <div class="caption font-weight-bold blue--text">DEC 2020 -</div>
                <div class="caption font-weight-bold blue--text">PRESENT</div>
              </v-flex>
              <v-flex class="pl-2">
                <strong>Volunteer</strong>
                <div class="caption mb-2">Township Maglaj</div>
              </v-flex>
            </v-layout>
          </v-timeline-item>

        </v-timeline>
      </v-card-text>
    </v-flex>
    <v-layout row justify-center align-center wrap class="mt-4 pt-2">
      <v-flex xs12 sm12 md4 lg5 xl5 class="mx-2 pt-4">
        <h2>
          <span>Design </span>

          <span class="blue--text">Skills</span>
        </h2>
        <br>
        <strong>HTML/CSS</strong>
        <v-progress-linear v-model="buffer1" :buffer-value="bufferValue" color="blue" height="16"></v-progress-linear>
        <strong>Bootstrap/Vuetify</strong>
        <v-progress-linear v-model="buffer2" :buffer-value="bufferValue" color="blue" height="16"></v-progress-linear>
        <strong>Adobe Photoshop</strong>
        <v-progress-linear v-model="buffer3" :buffer-value="bufferValue" color="blue" height="16"></v-progress-linear>
      </v-flex>
      <v-flex xs12 sm12 md4 lg5 xl5 class="mx-2 pt-4">
        <h2>
          <span>Coding </span>
          <span class="blue--text">Skills</span>
        </h2>
        <br>
        <strong>Node.Js</strong>
        <v-progress-linear v-model="buffer4" :buffer-value="bufferValue" color="blue" height="16"></v-progress-linear>
        <strong>Vue.Js</strong>
        <v-progress-linear v-model="buffer5" :buffer-value="bufferValue" color="blue" height="16"></v-progress-linear>
        <strong>JavaScript</strong>
        <v-progress-linear v-model="buffer6" :buffer-value="bufferValue" color="blue" height="16"></v-progress-linear>
      </v-flex>
      <div class="mt-4 pt-2">
        <v-btn
          href="https://app.luminpdf.com/viewer/60acc201408b1e001138d8d0"
          target="_blank"
          color="blue"
          dark
          large
        >
          Download Resume
          <v-icon right dark>fas fa-file-download</v-icon>
        </v-btn>
      </div>
    </v-layout>
  </v-layout>
</template>

<script>
export default {
  metaInfo: {
    title: "Resume",
    titleTemplate: "%s ← CA DEV",
    meta: [
      { name: "viewport", content: "width=device-width, initial-scale=1" },
      {
        name: "description",
        content:
          "Vue NUXT HTML CSS JavaScript Design Adobe XD Photoshop Coding Skills Resume Work Web Developer Front-End"
      },
      { charset: "utf-8" },
      { property: "og:title", content: "Ahmed' Cvrčak" },
      { property: "og:site_name", content: "Ahmed' Cvrčak" },
      { property: "og:type", content: "website" },
      { property: "og:url", content: "https://cadev" },
      {
        property: "og:image",
        content: "https://i.imgur.com/Dcz2PGx.jpg"
      },
      {
        property: "og:description",
        content:
          "Vue NUXT HTML CSS JavaScript Design Adobe XD Photoshop Coding Skills Resume Work Web Developer Front-End"
      }
    ]
  },
  data() {
    return {
      value: 0,
      buffer1: 0,
      buffer2: 0,
      buffer3: 0,
      buffer4: 0,
      buffer5: 0,
      buffer6: 0,
      bufferValue: 100,
      interval: 0
    };
  },
  mounted() {
    this.startBuffer();
  },

  beforeDestroy() {
    clearInterval(this.interval);
  },

  methods: {
    startBuffer() {
      this.interval = setInterval(() => {
        this.buffer1 = 90;
        this.buffer2 = 90;
        this.buffer3 = 65;
        this.buffer4 = 85;
        this.buffer5 = 80;
        this.buffer6 = 90;
      }, 800);
    }
  }
};
</script>



