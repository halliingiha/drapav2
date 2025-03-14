<template>
  <div class="w-60 min-w-60 max-w-60 h-96 border rounded-md p-4 bg-gray-200">
    {{ props.name }}
  </div>
</template>

<script setup>
const props = defineProps({
  name: String,
});
</script>
