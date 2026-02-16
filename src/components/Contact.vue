documentation can be found here .

<script setup>
import { reactive } from "vue";
import { useVuelidate } from "@vuelidate/core";
import { email, required } from "@vuelidate/validators";

import { ref } from "vue";

const value = ref("Hello!");

const initialState = {
  name: "",
  email: "",
  select: null,
  checkbox: null,
};

const state = reactive({
  ...initialState,
});

const items = ["Item 1", "Item 2", "Item 3", "Item 4"];

const rules = {
  name: { required },
  email: { required, email },
  select: { required },
  items: { required },
  checkbox: { required },
  textArea: [(v) => v.length <= 25 || "Max 25 characters"],
};

const v$ = useVuelidate(rules, state);

function clear() {
  v$.value.$reset();

  for (const [key, value] of Object.entries(initialState)) {
    state[key] = value;
  }
}
</script>
<template>
  <v-divider
    color="primary"
    opacity=".7"
    thickness="10"
    variant="double"
    gradient
  >
    Contact
  </v-divider>
  <div
    class="contact fill-height"
    id="contact-section"
    style="scroll-margin-top: 6rem"
  >
    <div class="mb-8 text-center">
      <p pt="8" class="text-subtitle-1">
        Ready to transform your business with custom applications? Contact us
        today to discuss your project.
      </p>
    </div>
    <v-form v-model="valid">
      <v-container>
        <v-row>
          <v-col cols="12" md="4">
            <v-text-field
              v-model="firstname"
              :counter="10"
              :rules="nameRules"
              label="First name"
              required
            ></v-text-field>
          </v-col>

          <v-col cols="12" md="4">
            <v-text-field
              v-model="lastname"
              :counter="10"
              :rules="nameRules"
              label="Last name"
              required
            ></v-text-field>
          </v-col>

          <v-col cols="12" md="4">
            <v-text-field
              v-model="email"
              :rules="emailRules"
              label="E-mail"
              required
            ></v-text-field>
          </v-col>

          <v-container fluid>
            <v-textarea
              :model-value="value"
              :rules="rules"
              label="Text"
              counter
            ></v-textarea>
          </v-container>
        </v-row>
        <!-- <div class="d-flex flex-column">
          <v-btn class="mt-4" color="success" block @click="validate">
            Validate
          </v-btn>

          <v-btn class="mt-4" color="error" block @click="reset">
            Reset Form
          </v-btn>

          <v-btn class="mt-4" color="warning" block @click="resetValidation">
            Reset Validation
          </v-btn>
        </div> -->
        <v-btn class="me-4" @click="v$.$validate"> submit </v-btn>
        <v-btn @click="clear"> clear </v-btn>
      </v-container>
    </v-form>
  </div>
</template>
<script>
export default {
  data: () => ({
    valid: false,
    firstname: "",
    lastname: "",
    nameRules: [
      (value) => {
        if (value) return true;

        return "Name is required.";
      },
      (value) => {
        if (value?.length <= 10) return true;

        return "Name must be less than 10 characters.";
      },
    ],
    email: "",
    emailRules: [
      (value) => {
        if (value) return true;

        return "E-mail is required.";
      },
      (value) => {
        if (/.+@.+\..+/.test(value)) return true;

        return "E-mail must be valid.";
      },
    ],
  }),
};
</script>
