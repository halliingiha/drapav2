<template>
  <div class="relative w-full h-[70vh] sm:h-[800px] overflow-hidden">
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
      <img
        class="absolute opacity-10 transition-all duration-1000 ease-in-out"
        src="/DRapaLOGO_WHITE@2x.png"
        :style="logoStyle"
        alt="logo"
      />
    </div>
  </div>
</template>

<script setup>
import { onMounted, ref } from "vue";

const logoLeft = ref(0);
const logoTop = ref(0);
const logoClass = ref("w-full h-auto"); // Start as full screen logo
const logoStyle = ref({
  width: "100%",
  height: "auto",
  top: "0px",
  left: "0px",
});

onMounted(() => {
  setTimeout(() => {
    logoStyle.value = {
      width: "300px",
      height: "auto",
      top: "16px", // Top-4 in Tailwind is 16px
      left: "16px", // Left-4 in Tailwind is 16px
      position: "absolute",
    };
  }, 2000);
});
</script>
