<template>
  <div class="home">
    <CounterWithStore msg="Welcome to Your Vue.js App" />
    <Sum />
  </div>
</template>

<script>
// @ is an alias to /src
import CounterWithStore from "@/components/CounterWithStore.vue";
import Sum from "@/components/Sum.vue";

export default {
  name: "Home",
  components: {
    CounterWithStore,
    Sum
  }
};
</script>
