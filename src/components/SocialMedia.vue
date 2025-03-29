<template>
  <div
    class="w-full flex gap-4 p-4 flex-col md:flex-wrap items-center justify-center mt-10 mb-24"
    ref="socialMediaSection"
  >
    <div class="flex flex-row gap-6 w-full h-10 items-center justify-center">
      <a
        v-for="item in mediaItems"
        :key="item.name"
        :href="item.link"
        target="_blank"
        class="hover:scale-110 transition-all"
      >
        <i :class="[item.icon, 'fa-2xl', 'text-zinc-500', item.hoverColor]" />
      </a>
    </div>

    <div class="w-full flex items-center justify-center flex-col gap-6">
      <div class="w-full flex justify-center">
        <iframe
          style="border-radius: 12px"
          src="https://open.spotify.com/embed/artist/6AVM9rg36bwti89n0X7qNw?utm_source=generator&theme=0"
          class="w-full md:w-[560px] h-[352px] shadow-md"
          frameBorder="0"
          allowfullscreen=""
          allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture"
          loading="lazy"
        ></iframe>
      </div>
      <div class="w-full flex justify-center rounded-lg overflow-hidden">
        <iframe
          width="560"
          height="315"
          class="w-full md:w-[560px] h-[352px] shadow-md"
          src="https://www.youtube.com/embed/RkT_ASKoi9A?si=akxiIMm-2LiDmS_6"
          title="YouTube video player"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
          referrerpolicy="strict-origin-when-cross-origin"
          allowfullscreen
        ></iframe>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
const mediaItems = ref([
  {
    name: "Facebook",
    link: "https://www.facebook.com/drapa.music",
    icon: "fab fa-facebook",
    hoverColor: "hover:text-blue-500/30",
  },
  {
    name: "Instagram",
    link: "https://www.instagram.com/drapa.music?utm_source=ig_web_button_share_sheet&igsh=ZDNlZDc0MzIxNw==",
    icon: "fab fa-instagram",
    hoverColor: "hover:text-orange-500/30",
  },
  {
    name: "Youtube",
    link: "https://www.instagram.com/drapa.music?utm_source=ig_web_button_share_sheet&igsh=ZDNlZDc0MzIxNw==",
    icon: "fab fa-youtube",
    hoverColor: "hover:text-red-500/30",
  },
  {
    name: "Spotify",
    link: "https://open.spotify.com/artist/6AVM9rg36bwti89n0X7qNw?si=X9QY52xlTYOdWJAYw-33hg",
    icon: "fab fa-spotify",
    hoverColor: "hover:text-green-500/30",
  },
]);
</script>
