<template>
  <!-- <button @click="increment">Count is: {{ state.count }}</button> -->
  <h1>{{ count }}</h1>
  <h1>{{ msg }}</h1>
</template>

<script>
import { reactive, toRefs } from "vue";

export default {
  setup() {
    const state = reactive({
      count: 20,
      msg: "hello world",
    });

    return {
      ...toRefs(state),
    };
  },
};
</script>
