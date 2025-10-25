<template>
  <section class="signupcontainer">
    <LoginField />
    <router-link to="/signup" class="signup-link">
      Don't have an account? Sign up
    </router-link>
  </section>
</template>

<script>
import LoginField from "../components/LoginField.vue";

export default {
  name: "Login",
  components: {
    LoginField,
  },
};
</script>