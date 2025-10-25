<template>
  <section class="ticket-list-container">
    <div
      v-for="(ticket, index) in safeList"
      :key="index"
      class="ticket-list"
    >
      <h2>{{ ticket.title }}</h2>
      <p>{{ ticket.description }}</p>

      <p>
        Status:
        <span :class="`status-badge status-${ticket.status}`">
          {{ ticket.status.replace('_', ' ') }}
        </span>
      </p>

      <div class="actn-btn">
        <button class="edit" @click="handleEdit(index)">Edit</button>
        <button class="delete" @click="handleDelete(ticket.title)">Delete</button>
      </div>
    </div>
  </section>
</template>

<script>
import { computed } from "vue";

export default {
  name: "TicketList",
  props: {
    ticketCreationList: {
      type: Array,
      default: () => [],
    },
    handleDelete: {
      type: Function,
      required: true,
    },
    handleEdit: {
      type: Function,
      required: true,
    },
  },
  setup(props) {
    const safeList = computed(() =>
      Array.isArray(props.ticketCreationList) ? props.ticketCreationList : []
    );

    return { safeList, ...props };
  },
};
</script>
