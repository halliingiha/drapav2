<template>
  <VideoBackground />
  <!-- <div ref="navPlaceholder" class="h-12"></div> -->
  <NavBar />
  <Members />
</template>

<script setup>
import { RouterLink, RouterView } from "vue-router";
import Members from "./components/Members.vue";
import VideoBackground from "./components/VideoBackground.vue";
import NavBar from "./components/NavBar.vue";
</script>

<style scoped></style>
