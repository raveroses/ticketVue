<template>
  <section class="sidebar-container">
    <StatusList :ticketCreationList="ticketCreationList" />

    <div class="second-sidebar-container">
      <div class="sidebar">
        <div class="top">
          <div class="icon">
            <!-- You can use an icon library like vue-icons if needed -->
            <span>📊</span>
          </div>
          <h2>Dashboard</h2>
        </div>

        <Sidebar :isOpen="isOpen" :handlleOpeningTab="handlleOpeningTab" />
      </div>

      <div class="creation">
        <TicketCreation
          v-if="isOpen === 'Create Ticket'"
          :ticketCreation="ticketCreation"
          :handleTicketOnchange="handleTicketOnchange"
          :handleTicketCreation="handleTicketCreation"
        />
        <TicketList
          v-else
          :ticketCreationList="ticketCreationList"
          :handleDelete="handleDelete"
          :handleEdit="handleEdit"
        />
      </div>
    </div>
  </section>
</template>

<script>
import { ref } from "vue";
import Sidebar from "../components/Sidebar.vue";
import TicketCreation from "../components/TicketCreation.vue";
import TicketList from "../components/TicketList.vue";
import StatusList from "../components/StatusList.vue";

export default {
  name: "Dashboard",
  components: {
    Sidebar,
    TicketCreation,
    TicketList,
    StatusList,
  },
  setup() {
    const ticketCreation = ref({
      title: "",
      description: "",
      status: "",
    });

    const ticketCreationList = ref([]);
    try {
      const stored = localStorage.getItem("store");
      const parsed = stored ? JSON.parse(stored) : [];
      ticketCreationList.value = Array.isArray(parsed) ? parsed : [];
    } catch (err) {
      console.error(err);
    }

    const editIndex = ref(null);
    const isOpen = ref("Create Ticket");

    const handleTicketOnchange = (e) => {
      const { name, value } = e.target;
      ticketCreation.value = { ...ticketCreation.value, [name]: value };
    };

    const handleTicketCreation = (e) => {
      e.preventDefault();

      if (
        !ticketCreation.value.title ||
        !ticketCreation.value.description ||
        !ticketCreation.value.status
      ) {
        alert("Please, check all fields");
        return;
      }

      let updatedList = [];

      if (editIndex.value !== null) {
        updatedList = ticketCreationList.value.map((ticket, index) =>
          index === editIndex.value ? ticketCreation.value : ticket
        );
        editIndex.value = null;
        alert("Ticket updated successfully");
      } else {
        updatedList = [...ticketCreationList.value, ticketCreation.value];
      }

      ticketCreationList.value = updatedList;
      localStorage.setItem("store", JSON.stringify(updatedList));
      ticketCreation.value = { title: "", description: "", status: "" };
    };

    const handleDelete = (value) => {
      const updatedList = ticketCreationList.value.filter(
        (ticket) => ticket.title !== value
      );
      ticketCreationList.value = updatedList;
      localStorage.setItem("store", JSON.stringify(updatedList));
      alert("Ticket deleted successfully");
    };

    const handleEdit = (index) => {
      const ticketToEdit = ticketCreationList.value[index];
      ticketCreation.value = ticketToEdit;
      editIndex.value = index;
      alert("Ticket edited successfully");
    };

    const handlleOpeningTab = (value) => {
      isOpen.value = value;
    };

    return {
      ticketCreation,
      ticketCreationList,
      editIndex,
      isOpen,
      handleTicketOnchange,
      handleTicketCreation,
      handleDelete,
      handleEdit,
      handlleOpeningTab,
    };
  },
};
</script>
