<template>
  <h1 class="text-3xl">{{ text }}</h1>
</template>

<script setup>
  defineProps({
    text: {
      type: String,
      required: true,
    },
  });
</script>
