<template>
  <div>
    <AtomCounter />
  </div>
</template>

<script>
import AtomCounter from "@/components/AtomCounter.vue";

export default {
  name: "CountView",
  components: {
    AtomCounter,
  },
  mounted() {
    console.log("Mounted:", window.history);
  },
  updated() {
    console.log("Updated", window.history);
  },
};
</script>

<style scoped></style>
