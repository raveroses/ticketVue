<template>
  <div class="hero-section">
    <div class="circle"></div>
    <div class="texts">
      <h2>Manage Your Ticket with Ease</h2>
      <p>Track, update, and resolve issues faster.</p>

      <div class="btns">
        <button @click="handleGetStarted">Get Started</button>
        <button @click="handleLogin">Login</button>
      </div>
    </div>
    <div class="image">
      <img src="/ticket.jpg" alt="hero-section" />
    </div>
  </div>
</template>

<script>
import { useRouter } from "vue-router";

export default {
  name: "Herosection",
  setup() {
    const router = useRouter();

    const goToSignup = () => {
      router.push("/signup");
    };

    const goToLogin = () => {
      router.push("/login");
    };

    return { goToSignup, goToLogin };
  },
};
</script>
