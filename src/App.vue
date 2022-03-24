<template>
  <div class="container mx-auto p-4"></div>
  <bankVue />
</template>

<script>
import counter from "./components/counter.vue";
import bankVue from "./components/bank.vue";
import colorNumberVue from "./components/colorNumber.vue";
export default {
  components: {
    counter,
    bankVue,
    colorNumberVue,
  },
  data() {
    return {};
  },
};
</script>

<style></style>
