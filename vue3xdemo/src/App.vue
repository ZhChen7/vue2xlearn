<template>
  <div>
    <h1 @click="handlNum">{{ state.count }}</h1>
    <h2>{{ double }}</h2>
    <input type="text" v-model="state.message" />
    <p>{{ state.message }}</p>
    <div id="v-model-select-dynamic" class="demo">
      <select v-model="state.selected">
        <option
          v-for="option in state.options"
          :value="option.value"
          :key="option"
        >
          {{ option.text }}
        </option>
      </select>
      <span>Selected: {{ state.selected }}</span>
    </div>
  </div>
</template>

<script>
import { computed, reactive, onMounted } from "vue";

export default {
  setup() {
    const state = reactive({
      count: 1,
      message: "111",
      selected: "A",
      options: [
        { text: "One", value: "A" },
        { text: "Two", value: "B" },
        { text: "Three", value: "C" },
      ],
    });

    onMounted(() => {
      console.log("component is mounted!");
    });

    const double = computed(() => state.count * 2);

    function handlNum() {
      state.count++;
    }

    return {
      state,
      handlNum,
      double,
    };
  },
};
</script>

<style lang="scss" scoped></style>
