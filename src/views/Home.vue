<template>
  <div class="container">
    <Herosection />
    <div>
      <Cards />
    </div>
  </div>
</template>

<script>
import Herosection from "../components/Herosection.vue";
import Cards from "../components/Cards.vue";
import { onMounted } from "vue";
import { useRouter } from "vue-router";
export default {
  name: "Home",
  components: {
    Herosection,
    Cards,
  },

  setup() {
    const router = useRouter();

    onMounted(() => {
      setTimeout(() => {
        const isUserLogin = localStorage.getItem("store");
        if (!isUserLogin) {
          router.push("/signup");
        }
      }, 1000);
    });
  },
};
</script>
