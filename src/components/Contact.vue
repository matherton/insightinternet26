<script setup>
import { reactive, ref } from "vue";
import { useVuelidate } from "@vuelidate/core";
import { email as emailValidator, required } from "@vuelidate/validators";

const initialState = {
  firstname: "",
  lastname: "",
  email: "",
  textArea: "",
};

const state = reactive({ ...initialState });

const nameRules = [
  (value) => !!value || "Name is required.",
  (value) => value?.length <= 20 || "Name must be less than 20 characters.",
];

const emailRules = [
  (value) => !!value || "E-mail is required.",
  (value) => /.+@.+\..+/.test(value) || "E-mail must be valid.",
];

// NEW: validation rules for the message textarea
const messageRules = [(value) => !!value || "Message is required."];

const rules = {
  firstname: { required },
  lastname: { required },
  email: { required, email: emailValidator },
  textArea: { required },
};

const v$ = useVuelidate(rules, state);

const form = ref(null);

async function submit() {
  await v$.value.$validate();
}

function clear() {
  v$.value.$reset();

  for (const [key, value] of Object.entries(initialState)) {
    state[key] = value;
  }

  form.value?.reset();
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

  <div class="contact" id="contact-section" style="scroll-margin-top: 6rem">
    <div class="mb-8 text-center">
      <p class="text-subtitle-1">
        Ready to transform your business with custom applications? Contact us
        today to discuss your project.
      </p>
    </div>

    <v-form ref="form">
      <v-container>
        <v-row>
          <v-col cols="12" md="4">
            <v-text-field
              v-model="state.firstname"
              :counter="20"
              :rules="nameRules"
              label="First name"
              required
            ></v-text-field>
          </v-col>

          <v-col cols="12" md="4">
            <v-text-field
              v-model="state.lastname"
              :counter="20"
              :rules="nameRules"
              label="Last name"
              required
            ></v-text-field>
          </v-col>

          <v-col cols="12" md="4">
            <v-text-field
              v-model="state.email"
              :rules="emailRules"
              label="E-mail"
              required
            ></v-text-field>
          </v-col>

          <v-col cols="12">
            <v-textarea
              v-model="state.textArea"
              :rules="messageRules"
              label="Message"
              counter
              required
            ></v-textarea>
          </v-col>
        </v-row>

        <div class="formBtns">
          <v-btn @click="submit">Submit</v-btn>
          <v-btn @click="clear">Clear</v-btn>
        </div>
      </v-container>
    </v-form>
  </div>
</template>
<style scoped>
.formBtns {
  margin-top: 1rem;
}
.contact {
  padding: 2rem 0rem; /* ensures Contact form btn's are not hidden behind sticky footer */
}
</style>
