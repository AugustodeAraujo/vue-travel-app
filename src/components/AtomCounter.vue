<template>
  <div>
    <h1>{{ count }}</h1>
    <button @click="increaseCount">Increase</button>
    <button @click="decreaseCount">Decrease</button>
  </div>
</template>

<script>
export default {
  name: "AtomCounter",
  data() {
    return {
      count: 0,
    };
  },
  mounted() {
    console.log("Mounted:", window.history);
  },
  updated() {
    console.log("Updated", window.history);
  },
  methods: {
    increaseCount() {
      this.count++;
      const payload = {
        increaseCount: this.count,
      };

      window.history.pushState(payload, "increaseCounter", window.location);
    },
    decreaseCount() {
      this.count--;

      const payload = {
        decreaseCount: this.count,
      };
      window.history.pushState(payload, "decreaseCounter", window.location);
    },
  },
};
</script>
