<template>
  <section>
    <h2>Create your Ticket</h2>

    <form class="signupForm" @submit.prevent="handleTicketCreation">
      <div>
        <label for="title">Title</label>
        <input
          type="text"
          id="title"
          name="title"
          v-model="ticketCreation.title"
        />
      </div>

      <div>
        <label for="description">Description</label>
        <input
          type="text"
          id="description"
          name="description"
          v-model="ticketCreation.description"
        />
      </div>

      <div>
        <select name="status" id="status" v-model="ticketCreation.status">
          <option v-for="(status, index) in list" :key="index" :value="status">
            {{ status }}
          </option>
        </select>
      </div>

      <div>
        <button type="submit">Create</button>
      </div>
    </form>
  </section>
</template>

<script>
export default {
  name: "TicketCreation",
  props: {
    ticketCreation: {
      type: Object,
      required: true,
    },
    handleTicketOnchange: {
      type: Function,
      required: true,
    },
    handleTicketCreation: {
      type: Function,
      required: true,
    },
  },
  setup() {
    const list = ["Open", "Close", "In progress"];

    return { list };
  },
};
</script>
