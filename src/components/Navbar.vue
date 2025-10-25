<template>
  <header>
    <div class="logo">
      <h2>Diamond Ticket</h2>
    </div>

    <nav class="navbars">
      <router-link to="/login">Login</router-link>
      <router-link to="/signup">Get Started</router-link>
      <router-link to="/dashboard">Dashboard</router-link>
      <router-link to="/tickets">Ticket Management</router-link>
    </nav>

    <div class="mobile-nav" v-show="isOpen">
      <nav class="navbar">
        <button class="close-btn" @click="handleClose">×</button>
        <router-link to="/login" @click="handleClose">Login</router-link>
        <router-link to="/signup" @click="handleClose">Get Started</router-link>
        <router-link to="/dashboard" @click="handleClose"
          >Dashboard</router-link
        >
        <router-link to="/tickets" @click="handleClose"
          >Ticket Management</router-link
        >
      </nav>
    </div>

    <button class="hamburger" @click="handleOpen">☰</button>
  </header>
</template>

<script>
import { ref } from "vue";

export default {
  name: "Navbar",
  setup() {
    const isOpen = ref(false);

    const handleOpen = () => (isOpen.value = true);
    const handleClose = () => (isOpen.value = false);

    return { isOpen, handleOpen, handleClose };
  },
};
</script>
