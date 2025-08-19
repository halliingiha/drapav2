<template>
  <VideoBackground />
  <!-- <div ref="navPlaceholder" class="h-12"></div> -->
  <NavBar :scroll-to-section="scrollToSection" />
  <section ref="membersSection">
    <Members />
  </section>
  <section ref="socialMediaSection">
    <SocialMedia />
  </section>
  <section ref="aboutSection">
    <About />
  </section>
</template>

<script setup>
import { ref } from "vue";
import { RouterLink, RouterView } from "vue-router";
import Members from "./components/Members.vue";
import VideoBackground from "./components/VideoBackground.vue";
import NavBar from "./components/NavBar.vue";
import SocialMedia from "./components/SocialMedia.vue";
import About from "./components/About.vue";

const membersSection = ref(null);
const socialMediaSection = ref(null);
const aboutSection = ref(null);

const sectionRefs = {
  members: { ref: membersSection, offset: 82 },
  socialMedia: { ref: socialMediaSection, offset: 282 },
  about: { ref: aboutSection, offset: 382 },
  // Add more sections here easily
};

function scrollToSection(section) {
  const sectionData = sectionRefs[section];
  console.log(sectionData);
  if (sectionData && sectionData.ref) {
    console.log(sectionData.ref.value);
    const element = sectionData.ref.value;
    const offset = sectionData.offset;
    console.log(element);
    const elementTop = element.getBoundingClientRect().top + window.scrollY;
    const scrollPosition = elementTop - offset;

    window.scrollTo({
      top: scrollPosition,
      behavior: "smooth",
    });
  } else {
    console.warn(`No scroll target found for section: ${section}`);
  }
}
// function scrollToSection(section) {
//   console.log(section);
//   console.log(membersSection.value?.$el);
//   if (section === "members" && membersSection.value) {
//     const offset = 82; // adjust as needed
//     const elementTop =
//       membersSection.value?.$el.getBoundingClientRect().top + window.scrollY;
//     const scrollPosition = elementTop - offset;

//     window.scrollTo({
//       top: scrollPosition,
//       behavior: "smooth",
//     });
//   }
//   if (section === "socialMedia" && socialMediaSection.value) {
//     const offset = 182; // adjust as needed
//     const elementTop =
//       socialMediaSection.value?.$el.getBoundingClientRect().top +
//       window.scrollY;
//     const scrollPosition = elementTop - offset;

//     window.scrollTo({
//       top: scrollPosition,
//       behavior: "smooth",
//     });
//   }
// }
</script>

<style scoped></style>
