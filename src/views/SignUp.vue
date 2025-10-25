<template>
  <section class="signupcontainer">
    <h3>Please, Sign Up</h3>
    <Fields />
  </section>
</template>

<script>
import Fields from "../components/Fields.vue";

export default {
  name: "SignUp",
  components: {
    Fields,
  },
};
</script>
