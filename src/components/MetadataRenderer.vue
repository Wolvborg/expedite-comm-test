<template>
  <div>
    <component
      class="my-4"
      v-for="(component, index) in components"
      :is="resolveComponent(component.type)"
      v-bind="component.props"
      :key="index"
    />
  </div>
</template>

<script setup>
  import { ref, onMounted } from 'vue';
  import HeadingComponent from '@src/components/HeadingComponent.vue';
  import ImageComponent from '@src/components/ImageComponent.vue';
  import ButtonComponent from '@src/components/ButtonComponent.vue';
  import ListComponent from '@src/components/ListComponent.vue';
  import ParagraphComponent from '@src/components/ParagraphComponent.vue';
  import mockData from '@api/data.json';

  const components = ref([]);

  onMounted(async () => {
    // Simulating fetching JSON data (mock external source)
    const response = mockData;
    components.value = response.components;
  });

  // Function to resolve component based on metadata
  const resolveComponent = (type) => {
    const componentMap = {
      heading: HeadingComponent,
      image: ImageComponent,
      button: ButtonComponent,
      list: ListComponent,
      para: ParagraphComponent,
    };
    return componentMap[type] || null;
  };
</script>
