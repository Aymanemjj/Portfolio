<script setup>
import { computed } from 'vue'

const props = defineProps({
  project: {
    type: Object,
    required: true,
  },
})

const images = import.meta.glob('@/assets/ProjectsAssets/**/*.{png,jpg,jpeg,webp,gif,svg}', {
  eager: true,
  import: 'default',
})

const thumbnailSrc = computed(() => {
  const path = props.project.preview.thumbnail
  const match = Object.entries(images).find(([key]) => key.endsWith(path))
  return match?.[1] ?? ''
})

function sendToLink() {
  if (props.project.link) {
    window.open(props.project.link, '_blank')
  }
}
</script>

<template>
  <div class="group font-bold cursor-pointer" @click="sendToLink">
    <div class="p-1 border border-transparent group-hover:border-pl-secondary dark:group-hover:border-pd-secondary transition-colors duration-300">
        <img
          :src="thumbnailSrc"
          :alt="project.preview.alt || `${project.title} preview`"
          class="text-pl-text dark:text-pd-text w-full mx-auto h-auto transition-all duration-300"
          loading="lazy"
          decoding="async"
        />
    </div>
    <div class="flex flex-col justify-between p-1">
      <h3 class="text-xl text-pl-primary dark:text-pd-primary font-bold">{{ project.title }}</h3>
      <div class="flex justify-between">
        <p class="text-sm font-light text-justify text-pl-text dark:text-pd-text">{{ project.description }}</p>
      </div>
    </div>
  </div>
</template>