<template>
  <p v-for="(para, index) in paras" :key="index" :class="['mb-4', { [textColor]: para.dataFlow }]">
    {{ para.text }}
  </p>
</template>

<script setup>
  import { inject } from 'vue';

  defineProps({
    paras: {
      required: true,
    },
  });

  const textColor = inject('text-color');
</script>
