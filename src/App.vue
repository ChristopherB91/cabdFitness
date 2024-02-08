<template>
  <div class="min-h-screen flex flex-col">
    <Nav @switch-component="switchComponent" />
    <component :is="currentComponent"></component>
  </div>
</template>

<script setup>
import { ref } from "vue";
import Nav from "./components/Navbar.vue";
import Homepage from "./components/Homepage.vue";

const currentComponent = ref(Homepage);

const switchComponent = (componentName) => {
  currentComponent.value = componentName;
};
</script>

<style scoped></style>
