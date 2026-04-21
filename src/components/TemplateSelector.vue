<template>
  <div class="template-selector">
    <h2>Select a Restaurant Layout Template</h2>
    <div v-for="template in templates" :key="template.id" class="template">
      <img :src="template.image" alt="{{ template.name }} preview" />
      <h3>{{ template.name }}</h3>
      <p>{{ template.description }}</p>
      <ul>
        <li>Total Space: {{ template.totalSpace }}m²</li>
        <li>Dining Room: {{ template.diningRoom }}m²</li>
        <li>Kitchen/Fireplace: {{ template.kitchen }}m²</li>
        <li>Seats Capacity: {{ template.capacity }}</li>
      </ul>
      <button @click="loadTemplate(template)">Load Template</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      templates: [
        {
          id: 1,
          name: 'Template 1',
          totalSpace: 100,
          diningRoom: 60,
          kitchen: 40,
          capacity: 60,
          image: 'placeholder1.png',
          description: 'Modern and airy layout ideal for casual dining.',
        },
        {
          id: 2,
          name: 'Template 2',
          totalSpace: 100,
          diningRoom: 60,
          kitchen: 40,
          capacity: 60,
          image: 'placeholder2.png',
          description: 'Cozy layout with an intimate setting.',
        },
        {
          id: 3,
          name: 'Template 3',
          totalSpace: 100,
          diningRoom: 60,
          kitchen: 40,
          capacity: 60,
          image: 'placeholder3.png',
          description: 'Spacious layout perfect for large gatherings.',
        },
        {
          id: 4,
          name: 'Template 4',
          totalSpace: 100,
          diningRoom: 60,
          kitchen: 40,
          capacity: 60,
          image: 'placeholder4.png',
          description: 'Elegant layout for fine dining experiences.',
        },
        {
          id: 5,
          name: 'Template 5',
          totalSpace: 100,
          diningRoom: 60,
          kitchen: 40,
          capacity: 60,
          image: 'placeholder5.png',
          description: 'Urban chic layout with a trendy vibe.',
        },
      ],
    };
  },
  methods: {
    loadTemplate(template) {
      // Logic to load the selected template into the main editor
      this.$emit('template-selected', template);
    },
  },
};
</script>

<style scoped>
.template-selector {
  display: flex;
  flex-direction: column;
}
.template {
  border: 1px solid #ccc;
  padding: 16px;
  margin: 8px 0;
}
</style>