<template>
  <v-card class="contact-form-card" max-width="600" elevation="4" rounded="lg">
    <v-card-title class="text-h5 font-weight-bold pa-6 pb-2">
      Get in Touch
    </v-card-title>
    <v-card-subtitle class="px-6 pb-4">
      Fill out the form below and we'll get back to you shortly.
    </v-card-subtitle>

    <v-card-text class="px-6">
      <!-- Success Alert -->
      <v-alert
        v-if="submitStatus === 'success'"
        type="success"
        variant="tonal"
        class="mb-4"
        closable
        @click:close="submitStatus = null"
      >
        Your message was sent successfully! We'll be in touch soon.
      </v-alert>

      <!-- Error Alert -->
      <v-alert
        v-if="submitStatus === 'error'"
        type="error"
        variant="tonal"
        class="mb-4"
        closable
        @click:close="submitStatus = null"
      >
        {{ errorMessage }}
      </v-alert>

      <v-form
        ref="formRef"
        v-model="isFormValid"
        @submit.prevent="handleSubmit"
      >
        <v-row>
          <!-- First Name -->
          <v-col cols="12" sm="6">
            <v-text-field
              v-model="form.firstName"
              label="First Name"
              placeholder="Jane"
              variant="outlined"
              density="comfortable"
              prepend-inner-icon="mdi-account-outline"
              :rules="[rules.required, rules.minLength(2)]"
              :disabled="isSubmitting"
            />
          </v-col>

          <!-- Last Name -->
          <v-col cols="12" sm="6">
            <v-text-field
              v-model="form.lastName"
              label="Last Name"
              placeholder="Doe"
              variant="outlined"
              density="comfortable"
              prepend-inner-icon="mdi-account-outline"
              :rules="[rules.required, rules.minLength(2)]"
              :disabled="isSubmitting"
            />
          </v-col>

          <!-- Email -->
          <v-col cols="12">
            <v-text-field
              v-model="form.email"
              label="Email Address"
              placeholder="jane.doe@example.com"
              type="email"
              variant="outlined"
              density="comfortable"
              prepend-inner-icon="mdi-email-outline"
              :rules="[rules.required, rules.email]"
              :disabled="isSubmitting"
            />
          </v-col>

          <!-- Message -->
          <v-col cols="12">
            <v-textarea
              v-model="form.message"
              label="Message"
              placeholder="Write your message here..."
              variant="outlined"
              rows="5"
              prepend-inner-icon="mdi-message-text-outline"
              :rules="[rules.required, rules.minLength(10)]"
              :disabled="isSubmitting"
              counter
              maxlength="1000"
            />
          </v-col>
        </v-row>

        <!-- Submit Button -->
        <v-btn
          type="submit"
          color="primary"
          size="large"
          block
          :loading="isSubmitting"
          :disabled="!isFormValid || isSubmitting"
          class="mt-2 mb-2"
          prepend-icon="mdi-send"
        >
          Send Message
        </v-btn>
      </v-form>
    </v-card-text>
  </v-card>
</template>

<script setup>
import { ref, reactive } from "vue";

// ─────────────────────────────────────────────
// 🔑 REPLACE THIS with your Web3Forms access key
// Get one free at https://web3forms.com
// ─────────────────────────────────────────────
const WEB3FORMS_ACCESS_KEY = "eca3e792-1b5c-4e59-b132-2604d9c7efbf";

// Form state
const formRef = ref(null);
const isFormValid = ref(false);
const isSubmitting = ref(false);
const submitStatus = ref(null); // null | 'success' | 'error'
const errorMessage = ref("");

const form = reactive({
  firstName: "",
  lastName: "",
  email: "",
  message: "",
});

// Validation rules
const rules = {
  required: (v) => !!v?.trim() || "This field is required.",
  email: (v) =>
    /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(v) ||
    "Please enter a valid email address.",
  minLength: (min) => (v) =>
    (v && v.trim().length >= min) || `Must be at least ${min} characters.`,
};

// Submit handler
async function handleSubmit() {
  const { valid } = await formRef.value.validate();
  if (!valid) return;

  isSubmitting.value = true;
  submitStatus.value = null;
  errorMessage.value = "";

  try {
    const payload = {
      access_key: WEB3FORMS_ACCESS_KEY,
      name: `${form.firstName} ${form.lastName}`,
      email: form.email,
      message: form.message,
      // Optional: customize the subject line in your Gmail inbox
      subject: `New message from ${form.firstName} ${form.lastName}`,
      // Optional: bot honeypot field (leave blank)
      botcheck: "",
    };

    const response = await fetch("https://api.web3forms.com/submit", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
        Accept: "application/json",
      },
      body: JSON.stringify(payload),
    });

    const data = await response.json();

    if (response.ok && data.success) {
      submitStatus.value = "success";
      resetForm();
    } else {
      throw new Error(data.message || "Submission failed. Please try again.");
    }
  } catch (err) {
    submitStatus.value = "error";
    errorMessage.value =
      err.message || "Something went wrong. Please try again later.";
  } finally {
    isSubmitting.value = false;
  }
}

function resetForm() {
  form.firstName = "";
  form.lastName = "";
  form.email = "";
  form.message = "";
  formRef.value?.resetValidation();
}
</script>

<style scoped>
.contact-form-card {
  margin: 0 auto;
}
</style>
