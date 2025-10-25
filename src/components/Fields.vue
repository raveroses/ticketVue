<template>
  <form class="signupForm" @submit.prevent="handleSubmit">
    <div>
      <label for="fullName">Full Name</label>
      <input
        type="text"
        id="fullName"
        name="fullName"
        v-model="user.fullName"
      />
    </div>

    <div>
      <label for="email">Email</label>
      <input type="email" id="email" name="email" v-model="user.email" />
    </div>

    <div>
      <label for="password">Password</label>
      <input
        type="password"
        id="password"
        name="password"
        v-model="user.password"
      />
    </div>

    <div>
      <button type="submit">Sign Up</button>
    </div>
  </form>
</template>

<script>
import { ref } from "vue";
import { useRouter } from "vue-router";

export default {
  name: "Fields",
  setup() {
    const router = useRouter();

    const user = ref({
      fullName: "",
      email: "",
      password: "",
    });

    // Load stored data from localStorage
    try {
      const stored = localStorage.getItem("store");
      if (stored) user.value = JSON.parse(stored);
    } catch (err) {
      alert(err.message);
    }

    const handleSubmit = () => {
      if (!user.value.fullName || !user.value.email || !user.value.password) {
        alert("Please, check your fields");
        return;
      }

      localStorage.setItem("store", JSON.stringify(user.value));
      alert("Account created successfully");

      // Reset form
      user.value = { fullName: "", email: "", password: "" };

      setTimeout(() => {
        router.push("/login");
      }, 1000);
    };

    return { user, handleSubmit };
  },
};
</script>
