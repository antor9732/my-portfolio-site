<script setup>
const props = defineProps({
  title: String,
  description: String,
  tags: String,
  link: String,
  demoLabel: String,
  image: String,
});
</script>

<template>
  <div class="card h-100 shadow-lg border-0 rounded-4 bg-dark bg-opacity-50 text-white">
    <img v-if="image" :src="image" :alt="title" class="card-img-top rounded-top-4" style="object-fit:cover; max-height:260px; min-height:180px;" />
    <div class="card-body">
      <h5 class="card-title fw-bold mb-2">{{ title }}</h5>
      <p class="card-text mb-3">{{ description }}</p>
      <div class="mb-3">
        <span v-for="tag in tags.split(',')" :key="tag" class="badge bg-secondary me-1 mb-1">{{ tag.trim() }}</span>
      </div>
      <a :href="link" target="_blank" class="btn btn-sm btn-primary px-3">{{ demoLabel }}</a>
    </div>
  </div>
</template>