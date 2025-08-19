<template>
  <div
    class="group flex rounded-tr-[10rem] rounded-bl-[10rem] flex-wrap sm:flex-nowrap items-center justify-center overflow-hidden relative h-[40rem] w-full sm:w-[12rem] sm:rounded-t-2xl sm:rounded-b-2xl sm:hover:w-[25rem] sm:transition-all sm:duration-[500ms] ease-in-out"
    style="
      box-shadow: rgba(0, 0, 0, 0.25) 0px 6px 12px -2px,
        rgba(0, 0, 0, 0.3) 0px 3px 7px -3px;
    "
  >
    <!-- class="group flex rounded-tr-[10rem] shadow-2xl rounded-bl-[10rem] flex-wrap sm:flex-nowrap items-center justify-center overflow-hidden relative h-[40rem] w-full sm:w-[12rem] sm:shadow-2xl sm:rounded-tl-full sm:rounded-tr-full sm:rounded-br-full sm:rounded-bl-full sm:hover:w-[25rem] sm:hover:rounded-tr-none sm:hover:rounded-tl-none sm:transition-all sm:duration-[500ms] ease-in-out" -->
    <!-- {{ props.name }} -->
    <!-- <span
      class="absolute z-10 text-white text-8xl group-hover:opacity-0 transition-all duration-300"
    >
      <span class="absolute -rotate-90">{{ props.name }}</span>
      <span class="absolute rotate-0">{{ props.instrument }}</span>
    </span> -->
    <span
      class="absolute z-10 text-white/20 text-8xl transition-all duration-300 opacity-100 group-hover:opacity-0"
    >
      <span
        class="absolute -rotate-90 top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2"
      >
        {{ props.name }}
      </span>
    </span>

    <!-- Instrument (Hidden initially, Appears on hover) -->
    <span
      class="absolute z-10 text-white/20 text-6xl w-full h-full transition-all duration-300 opacity-0 group-hover:opacity-100"
    >
      <span class="absolute rotate-0 top-5 left-1/2 transform -translate-x-1/2">
        {{ props.instrument }}
      </span>
    </span>
    <!-- <img src="../assets/drapa.svg" class="h-full" /> -->
    <img
      :src="props.imgSource"
      class="opacity-30 absolute top-0 w-[70rem] h-full group-hover:opacity-100 duration-500"
      :style="{ left: props.leftPosition }"
      style="color: transparent; max-width: none; height: initial"
    />
  </div>
</template>

<script setup>
const props = defineProps({
  name: String,
  imgSource: String,
  leftPosition: String,
  instrument: String,
});
</script>
