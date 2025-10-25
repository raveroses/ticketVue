<template>
  <section class="sidebar-components">
    <div
      v-for="(item, index) in sidebardetails"
      :key="index"
      class="sidebar-flex"
      :class="{ logout: item.names === 'Log out' }"
      @click="onClick(item.names)"
    >
      <div class="icon">{{ item.icon }}</div>
      <h3>{{ item.names }}</h3>
    </div>
  </section>
</template>

<script>
import { ref } from "vue";
import { useRouter } from "vue-router";

export default {
  name: "Sidebar",
  props: {
    handlleOpeningTab: {
      type: Function,
      required: true,
    },
  },
  setup(props) {
    const router = useRouter();

    const sidebardetails = ref([
      { icon: "📃", names: "Ticket List" },
      { icon: "✏️", names: "Create Ticket" },
      { icon: "🚪", names: "Log out" },
    ]);

    const onClick = (name) => {
      if (name === "Log out") {
        localStorage.removeItem("Loginstore");
        router.push("/login");
      } else {
        props.handlleOpeningTab(name);
      }
    };

    return {
      sidebardetails,
      onClick,
    };
  },
};
</script>

