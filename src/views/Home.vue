<template>
  <div class="container">
    <HeroSection />
    <div>
      <Cards />
    </div>
  </div>
</template>

<script>
import Herosection from "../components/Herocection.vue";
import Cards from "../components/Cards.vue";
export default {
  name: "Home",
  components: {
    Herocection,
    Cards,
  },
};
</script>
