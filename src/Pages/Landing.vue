<template>
  <section v-if="landing">
    <div class="landing-card-container">
      <div class="text-side" role="content">
        <h1>Stay updated!</h1>
        <p>
          Join 60,000+ product managers receiving monthly updates on:
        </p>
        <div class="tick-list">
          <span class="list">
            <img src="../assets/icon-list.svg" alt="list">
            <p>Product discovery abd building what matters</p>
          </span>
          <span class="list">
            <img src="../assets/icon-list.svg" alt="list">
            <p>Product discovery abd building what matters</p>
          </span>
          <span class="list">
            <img src="../assets/icon-list.svg" alt="list">
            <p>Product discovery abd building what matters</p>
          </span>
        </div>

        <form @submit.prevent="submitForm" class="send-email">
          <label for="email">Email address</label>
          <span v-if="validationError" class="error-message">Valid email required</span>
          <input type="text" name="email" v-model="email" :class="{ 'input-error ': validationError }"
            placeholder="email@company.com" />
          <a href="#" @click="submitForm">
            <div class="action-button">
              Subscribe to monthly newsletter
            </div>
          </a>
        </form>
      </div>
      <div class="image-side" role="attachments">
        <img class="desktop" src="../assets/illustration-sign-up-desktop.svg" alt="image" role="img">
        <img class="mobile" src="../assets/illustration-sign-up-mobile.svg" alt="image" role="img">
      </div>
    </div>
  </section>
  <section v-if="success">
    <div class="success-card-container">
      <img src="../assets/icon-success.svg" alt="list">
      <h1>Thanks for subscribing!</h1>
      <p>
        A confirmation email has been sent to <strong v-if="email">{{ email }},</strong> Please open it and click the
        button inside
        to
        confirm your subscription.
      </p>

      <a href="#" @click="dissmissSuccess">
        <div class="action-button">
          Dismiss message
        </div>
      </a>
    </div>
  </section>
</template>
  
<script>
export default {
  name: 'App',

  data() {
    return {
      landing: true,
      success: false,
      email: "",
      validationError: false,
    };
  },
  methods: {
    submitForm() {
      // Basic email validation
      if (!this.isValidEmail(this.email)) {
        this.validationError = true;
      } else {
        // Handle form submission here (e.g., send data to the server)
        this.landing = false;
        this.success = true;
        this.validationError = false;
      }
    },

    isValidEmail(email) {
      // Basic email validation regex
      const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
      return emailRegex.test(email);
    },

    dissmissSuccess() {
      this.landing = true;
      this.success = false;
    }
  }
}
</script>