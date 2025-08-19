<template>
  <div
    class="w-full flex gap-6 p-4 md:flex-row flex-col md:flex-wrap items-center justify-center mt-10 mb-[30px]"
    ref="membersSection"
  >
    <section
      class="flex flex-wrap sm:flex-nowrap gap-2 justify-around scroll-mt-[10rem] top-[30rem] h-auto w-full sm:px-10 sm:gap-0"
    >
      <MemberCard
        v-for="member in members"
        :name="member.name"
        :imgSource="member.imgSource"
        :leftPosition="member.leftPosition"
        :instrument="member.instrument"
      />
    </section>
  </div>
</template>

<script setup lang="ts">
import MemberCard from "./MemberCard.vue";

import { ref } from "vue";
// import jakobImg from "@/assets/members/jakob.jpg";

const members = ref([
  {
    name: "Jakob",
    imgSource: "/members/jakob.jpg",
    leftPosition: "30",
    instrument: "Guitar",
  },
  {
    name: "Örn",
    imgSource: "/members/orn.jpg",
    leftPosition: "30",
    instrument: "Drums",
  },
  {
    name: "Sævar",
    imgSource: "/members/saevar.jpg",
    leftPosition: "-20rem",
    instrument: "Vocals",
  },
  {
    name: "Tómas",
    imgSource: "/members/tomas.jpg",
    leftPosition: "30",
    instrument: "Guitar",
  },
  {
    name: "Haraldur",
    imgSource: "/members/halli.jpg",
    leftPosition: "-20rem",
    instrument: "Bass",
  },
]);
</script>
