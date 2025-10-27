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
export default {
  name: "Home",
  components: {
    Herosection,
    Cards,
  },
};
</script>
