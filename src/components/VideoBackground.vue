<template>
  <div class="relative w-full h-[70vh] overflow-hidden">
    <video
      class="absolute top-0 left-0 w-full h-full object-cover z-0 brightness-0.5"
      autoplay
      muted
      loop
      playsinline
      src="/IgnoredWeb.mp4"
    ></video>
    <div
      class="relative z-10 flex items-center justify-center w-full h-full text-white"
    >
      <img class="relative h-auto max-h-96 opacity-10"
      src="/DRapaLOGO_WHITE@2x.png" :class="{}" alt="logo"
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const logoLeft = ref(0);
const logoTop = ref(0);
</script>
