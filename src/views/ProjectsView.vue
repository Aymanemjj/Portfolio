<script setup lang="ts">
import ProjectCard from "@/components/ProjectCard.vue";
import PROJECTS from '@/data/projects.json'

const PROGRAMING_COUNT = PROJECTS.programing.length;
</script>

<template>
    <main class="flex flex-col gap-16">
        <div class="font-bold flex text-3xl">
            <h2 class="text-pl-primary dark:text-pd-primary">
                Projects <span class="text-pl-secondary dark:text-pd-secondary">[{{ PROGRAMING_COUNT }}]</span>
            </h2>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 xl:grid-cols-3 gap-8  mx-auto">
            <ProjectCard v-for="project in PROJECTS.programing" :key="project.title" :project="project" />
        </div>
    </main>
</template>
