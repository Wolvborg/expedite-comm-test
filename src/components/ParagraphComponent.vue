<template>
  <p v-for="(para, index) in paras" :key="index" class="mb-4">
    {{ para }}
  </p>
</template>

<script setup>
  defineProps({
    paras: {
      required: true,
    },
  });
</script>
