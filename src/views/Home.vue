<template>
  <div class="container">
    <HeroSection />
    <div>
      <Cards />
    </div>
  </div>
</template>

<script>
import HeroSection from "../components/HeroSection.vue";
import Cards from "../components/Cards.vue";
export default {
  name: "Home",
  components: {
    HeroSection,
    Cards,
  },
};
</script>
