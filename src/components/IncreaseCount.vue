<template>
  <div>
    <h1>{{ count }}</h1>
    <button @click="ïncreaseCount;">Increase Counter</button>
  </div>
</template>

<script>
export default {
  name: "IncreaseCount",
  data() {
    return {
      count: 0,
    };
  },
  updated() {
    console.log("Counte updated:", window.history);
  },
  methods: {
    increaseCount() {
      this.count++;

      const objState = {
        count: this.count,
      };

      window.history.pushState(objState, "counter");
    },
  },
};
</script>
