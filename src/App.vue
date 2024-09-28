<template>
  <MetadataRenderer class="container mx-auto" />
</template>

<script setup>
  import { provide } from 'vue';

  import MetadataRenderer from './components/MetadataRenderer.vue';

  const textColor = 'text-green-500';
  provide('text-color', textColor);
</script>
