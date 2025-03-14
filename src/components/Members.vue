<template>
  <div
    class="w-full flex gap-6 p-4 md:flex-row flex-col md:flex-wrap items-center justify-center"
  >
    <MemberCard v-for="member in members" :name="member.name" />
  </div>
</template>

<script setup lang="ts">
import MemberCard from "./MemberCard.vue";
import { ref } from "vue";

const members = ref([
  {
    name: "Jakob",
  },
  {
    name: "Örn",
  },
  {
    name: "Sævar",
  },
  {
    name: "Tómas",
  },
  {
    name: "Haraldur",
  },
]);
</script>
