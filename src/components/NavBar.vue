<template>
  <div
    ref="navbar"
    class="flex justify-center items-center h-12 w-full bg-zinc-700 gap-3 shadow-2xl"
    :class="
      isSticky
        ? 'fixed top-0 left-0 shadow-md z-50 transform translate-y-0'
        : 'relative transform translate-y-[0px]'
    "
  >
    <span
      v-for="item in navItem"
      class="px-3 py-1 rounded-2xl hover:bg-zinc-900 hover:cursor-pointer text-zinc-500 text-xs md:text-[1rem]"
      :class="
        selectedNavItem === item.label
          ? 'bg-zinc-900 border border-gray-400/50'
          : 'bg-zinc-800'
      "
      @click="selectNavItem(item.label), scrollToSection(item.scrollTo)"
      >{{ item.label }}</span
    >
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";
const selectedNavItem = ref(null);
const isSticky = ref(false);
const navbar = ref(null);
const lastScrollY = ref(0);

defineProps({
  scrollToSection: Function,
});

const navItem = ref([
  {
    label: "Members",
    scrollTo: "members",
  },
  {
    label: "Social Media",
    scrollTo: "socialMedia",
  },
  {
    label: "About",
  },
  {
    label: "Contact",
  },
]);

function selectNavItem(navItemLabel) {
  console.log(navItemLabel);

  selectedNavItem.value = navItemLabel; // Fix this line
}

const handleScroll = () => {
  const currentScrollY = window.scrollY;
  console.log("currentScrollY: ", currentScrollY);
  console.log("lastScrollY: ", lastScrollY.value);
  if (navbar.value) {
    const rect = navbar.value.getBoundingClientRect();

    // Stick when scrolling down, release when scrolling up
    if (currentScrollY > lastScrollY.value && rect.top <= 0) {
      isSticky.value = true; // Stick when scrolling down
    } else if (currentScrollY < lastScrollY.value && currentScrollY < 800) {
      isSticky.value = false; // Release when scrolling up near the top
    }

    lastScrollY.value = currentScrollY;
  }
};

onMounted(() => {
  window.addEventListener("scroll", handleScroll);
});

onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll);
});
</script>
