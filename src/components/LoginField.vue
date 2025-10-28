<template>
  <form class="signupForm" @submit.prevent="handleSubmit">
    <div>
      <label for="email">Email</label>
      <input type="email" id="email" name="email" v-model="userLogin.email" />
    </div>

    <div>
      <label for="password">Password</label>
      <input
        type="password"
        id="password"
        name="password"
        v-model="userLogin.password"
      />
    </div>

    <div>
      <button type="submit">Login</button>
    </div>
  </form>
</template>

<script>
import { ref } from "vue";
import { useRouter } from "vue-router";

export default {
  name: "LoginField",
  setup() {
    const router = useRouter();

    const userLogin = ref({
      email: "",
      password: "",
    });

    const fetchUserDetail = ref({
      email: "",
      password: "",
    });

    try {
      const storedLogin = localStorage.getItem("Loginstore");
      if (storedLogin) userLogin.value = JSON.parse(storedLogin);
    } catch (err) {
      alert(err.message);
    }

    try {
      const storedUser = localStorage.getItem("store");
      if (storedUser) fetchUserDetail.value = JSON.parse(storedUser);
    } catch (err) {
      alert(err.message);
    }

    const handleSubmit = () => {
      if (!fetchUserDetail.value.email || !fetchUserDetail.value.password) {
        alert("No registered user found. Please sign up first.");
        return;
      }

      // check login credentials
      if (
        userLogin.value.email !== fetchUserDetail.value.email ||
        userLogin.value.password !== fetchUserDetail.value.password
      ) {
        alert("Please, check your fields");
        return;
      }

      localStorage.setItem("Loginstore", JSON.stringify(userLogin.value));
      alert("Login successfully");

      // Reset form
      userLogin.value = { email: "", password: "" };

      setTimeout(() => {
        router.push("/");
      }, 1000);
    };

    return {
      userLogin,
      handleSubmit,
    };
  },
};
</script>
