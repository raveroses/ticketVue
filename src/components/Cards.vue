<template>
  <div class="testimonials-container">
    <div
      class="testimonial-card"
      v-for="item in ticketTestimonials"
      :key="item.id"
    >
      <p class="testimonial-text">"{{ item.testimonial }}"</p>
      <h4 class="testimonial-name">{{ item.name }}</h4>
      <p class="testimonial-event">{{ item.event }}</p>
    </div>
  </div>
</template>
<script>
import { ref } from "vue";

export default {
  name: "Cards",
  setup() {
    const ticketTestimonials = ref([
      {
        id: 1,
        name: "Alice Johnson",
        testimonial:
          "Booking my concert ticket was seamless! The process was quick and easy.",
        event: "Rock Concert 2025",
      },
      {
        id: 2,
        name: "Michael Smith",
        testimonial:
          "I loved how I could choose my seat online. Definitely booking again!",
        event: "Broadway Musical",
      },
      {
        id: 3,
        name: "Sophia Lee",
        testimonial:
          "The ticket confirmation was instant, and the app reminded me of the event. Very convenient.",
        event: "Tech Conference",
      },
    ]);

    return { ticketTestimonials };
  },
};
</script>
