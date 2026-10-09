<script setup lang="ts">
import ProjectCard from "@/components/SideProjectCard.vue";
import PROJECTS from '@/data/projects.json'

const SIDES_COUNT = PROJECTS.side.length;
</script>

<template>
    <main class="flex flex-col gap-16">
        <div class="font-bold flex text-3xl">
            <h2 class="text-pl-primary dark:text-pd-primary">
                Side <span class="text-pl-secondary dark:text-pd-secondary">[{{ SIDES_COUNT }}]</span>
            </h2>
        </div>

        <div class="columns-1 md:columns-2 xl:columns-3 gap-8">
            <div v-for="project in PROJECTS.side" :key="project.title" class="break-inside-avoid mb-8">
                <ProjectCard :project="project" />
            </div>
        </div>
    </main>
</template>
