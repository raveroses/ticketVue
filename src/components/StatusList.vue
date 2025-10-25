<template>
  <section class="status-list">
    <div
      v-for="(status, index) in statusLists"
      :key="index"
      class="status-item"
    >
      <p>{{ status.label }}</p>
      <h3>{{ status.value }}</h3>
    </div>
  </section>
</template>

<script>
import { computed } from "vue";

export default {
  name: "StatusList",
  props: {
    ticketCreationList: {
      type: Array,
      default: () => [],
    },
  },
  setup(props) {
    const safeList = computed(() =>
      Array.isArray(props.ticketCreationList) ? props.ticketCreationList : []
    );

    const statusLists = computed(() => [
      { label: "Total Tickets", value: safeList.value.length },
      {
        label: "Open Tickets",
        value: safeList.value.filter((item) => item.status === "open").length,
      },
      {
        label: "Resolve Tickets",
        value: safeList.value.filter((item) => item.status === "closed").length,
      },
    ]);

    return { statusLists };
  },
};
</script>
