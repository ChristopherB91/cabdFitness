<template>
  <header class="border-solid border-green-800 border-b-4">
    <nav
      class="flex text-center text-celtic text-3xl list-none flex-col sm:justify-around sm:flex-row sm:items-center"
    >
      <div id="img" class="flex justify-center">
        <img
          src="../assets/logo.svg"
          alt="site logo"
          class="w-3/6 sm:w-full"
          @click="switchTo(Homepage)"
        />
      </div>
      <button @click="switchTo(Exercises)">
        <b>EXERCISES</b>
      </button>
      <button>
        <b>CONTACT</b>
      </button>
      <button>
        <b>DIETS</b>
      </button>
    </nav>
  </header>
</template>

<script setup>
import Homepage from "./Homepage.vue";
import Exercises from "./Exercises.vue";

const emit = defineEmits(["switch-component"]);

const switchTo = (componentName) => {
  emit("switch-component", componentName);
};
</script>

<style></style>
