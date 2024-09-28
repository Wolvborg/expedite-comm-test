<template>
  <img :src :alt :width :height />
</template>

<script setup>
  defineProps({
    src: {
      type: String,
      required: true,
    },
    alt: {
      type: String,
      required: false,
    },
    height: {
      type: Number,
      required: false,
    },
    width: {
      type: Number,
      required: false,
    },
  });
</script>
