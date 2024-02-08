<!-- Just practice -->
<script setup>
import { ref } from "vue";
const count = ref(0);
const minValue = ref(0);
const maxValue = ref(10);

const increment = () => {
  if (count.value < maxValue.value) {
    count.value++;
  } else {
    window.alert(`Cannot go above ${maxValue.value}`);
  }
};

const decrement = () => {
  if (count.value > minValue.value) {
    count.value--;
  } else {
    window.alert(`cannot go below ${minValue.value}`);
  }
};

const validateInput = () => {
  if (minValue.value >= maxValue.value) {
    window.alert("Min value must be less than max value.");
    minValue.value = 0;
    maxValue.value = 10;
  }
};
</script>

<template>
  <div class="flex justify-around">
    <div id="min" class="flex">
      <p>Min:</p>
      <input
        type="number"
        placeholder="min"
        v-model="minValue"
        @input="validateInput"
        class="text-center"
      />
    </div>
    <p>and</p>
    <div id="max" class="flex">
      <p>Max:</p>
      <input
        type="number"
        placeholder="max"
        v-model="maxValue"
        @input="validateInput"
        class="text-center"
      />
    </div>
  </div>
  <br />
  <div class="flex justify-around">
    <button
      @click="decrement(minValue)"
      class="border-solid border-black border-2 bg-gray-100 text-black text-5xl px-3"
      :disabled="count === minValue"
    >
      -
    </button>
    <p>{{ count }}</p>
    <button
      @click="increment(maxValue)"
      class="border-solid border-black border-2 bg-gray-100 text-black text-4xl px-3"
      :disabled="count === maxValue"
    >
      +
    </button>
  </div>
</template>

<style scoped></style>
