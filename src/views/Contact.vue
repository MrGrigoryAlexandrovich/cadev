<template>
  <v-container grid-list-xl>
    <v-layout row justify-center align-center wrap class="mt-4 pt-2">
      <v-flex xs12 sm12 md6 lg6 xl6>
        <h2 class="pb-4 mt-2">
          <span>GetIn</span>
          <span class="blue--text">Touch</span>
        </h2>
        <div class="py-4 subheading font-weight-bold">
          <v-icon large color="blue" left>fas fa-map-marker-alt</v-icon>
          <span>Maglaj,&nbsp;</span>
          <span class="blue--text">Bosnia & Herzegovina</span>
        </div>
        <div class="py-4 subheading font-weight-bold">
          <v-icon large color="blue" left>fas fa-envelope</v-icon>
          <span>ahmedcvrle@</span>
          <span class="blue--text">gmail.com</span>
        </div>
        <div class="py-4 subheading font-weight-bold">
          <v-icon large color="blue" left>fas fa-phone</v-icon>
          <span>+387&nbsp;</span>
          <span class="blue--text">60/339-4022</span>
        </div>
        <div class="py-4 subheading font-weight-bold">
          <v-icon large color="blue" left>fas fa-check</v-icon>
          <span>Freelance</span>
          <span class="blue--text"> Available</span>
        </div>
      </v-flex>

      <v-flex xs12 sm12 md6 lg6 xl6>
        <h2 class="pb-4 mb-4">
          <span>Contact</span>
          <span class="blue--text"> Form</span>
        </h2>

      <form class="contact-form" @submit.prevent="sendEmail">
   <v-text-field
            name="name"
            color="blue"
            background-color="transparent"
            v-model="name"
            :error-messages="nameErrors"
            label="Name"
            required
            @blur="$v.name.$touch()"
          ></v-text-field>
          <v-text-field
            type="email"
            color="blue"
            background-color="transparent"
            name="email"
            v-model="email"
            :error-messages="emailErrors"
            label="E-mail"
            required
            @blur="$v.email.$touch()"
          ></v-text-field>
          <v-textarea
            color="blue"
            background-color="transparent"
            :counter="200"
            :error-messages="bodyErrors"
            v-model="body"
            label="Textarea"
            name="body"
            @blur="$v.body.$touch()"
          ></v-textarea>
          <v-btn
            @click="submit"
            type="submit"
            color="blue"
            value="Send"
            class="white--text"
            :disabled=" (body.length<=20)"
          >SEND MESSAGE</v-btn>
          <v-btn @click="clear">clear</v-btn>
  </form>
      </v-flex>
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
    </v-layout>
  </v-container>
</template>

<script>
import emailjs from 'emailjs-com';
import { validationMixin } from "vuelidate";
import {
  required,
  maxLength,
  email,
  minLength
} from "vuelidate/lib/validators";
export default {
  metaInfo: {
    title: "Contact",
    titleTemplate: "%s ← CA DEV",
    meta: [
      { name: "viewport", content: "width=device-width, initial-scale=1" },
      {
        name: "description",
        content:
          "Ahmed Cvrčak's Contact Doboj Bosnia and Herzegovina Freelance Get in Touch ContactMe"
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
          "Ahmed Cvrčak's Contact Maglaj Bosnia and Herzegovina Freelance Get in Touch ContactMe"
      }
    ]
  },
  mixins: [validationMixin],
  validations: {
    name: { required, maxLength: maxLength(20) },
    email: { required, email },
    body: { required, minLength: minLength(20) }
  },
  data() {
    return {
      name: "",
      email: "",
      body: "",
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
  methods: {
    submit() {
      this.$v.$touch();
    },
    clear() {
      this.$v.$reset();
      this.name = "";
      this.email = "";
      this.body = "";
    },
        sendEmail () {
           emailjs.init('user_sMECxSGss2PbhW66dhkp5');
emailjs.send("service_dqrww8n","template_z3o2wxj",{
from_name: this.name,
to_name: "Ahmed Cvrčak",
email: this.email,
message: this.body,
})
    .then(function(response) {
      alert('email sent successfully')
    }, function(error) {
     alert('Server ERROR')
     console.log(error)
    });
    this.clear()
        }
  },
  computed: {
    nameErrors() {
      const errors = [];
      if (!this.$v.name.$dirty) return errors;
      !this.$v.name.maxLength &&
        errors.push("Name must be at most 20 characters long");
      !this.$v.name.required && errors.push("Name is required.");
      return errors;
    },
    emailErrors() {
      const errors = [];
      if (!this.$v.email.$dirty) return errors;
      !this.$v.email.email && errors.push("Must be valid e-mail");
      !this.$v.email.required && errors.push("E-mail is required");
      return errors;
    },
    bodyErrors() {
      const errors = [];
      if (!this.$v.body.$dirty) return errors;
      !this.$v.body.minLength &&
        errors.push("Text must be at least 20 characters long");
      !this.$v.body.required && errors.push("Text is required");
      return errors;
    }
  }
};
</script>

