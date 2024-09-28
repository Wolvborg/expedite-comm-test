<template>
  <component :is="tag" :class="listClass">
    <li v-for="(item, index) in items" :key="index">{{ item }}</li>
  </component>
</template>

<script setup>
  import { computed } from 'vue';
  const props = defineProps({
    items: {
      type: String,
      required: true,
    },
    order: {
      type: Boolean,
      required: false,
    },
  });

  const tag = computed(() => {
    return props.order ? 'ol' : 'ul';
  });
  const listClass = computed(() => {
    return props.order ? 'list-decimal' : 'list-disc';
  });
</script>
