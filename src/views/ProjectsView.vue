<script setup lang="ts">
import ProjectCard from "@/components/ProjectCard.vue";
import { ref } from "vue";
import PROJECTS from '@/data/projects.json'

const TAB = ref("programing");
const PROGRAMING_COUNT = PROJECTS.programing.length;
const OTHER_COUNT = PROJECTS.other.length;

function changeTab(tab: string) {
    TAB.value = tab;
}
</script>

<template>
    <main class="flex flex-col gap-16">
        <div class="text-p-lightBrown font-bold flex justify-around gap-4">
            <button
                @click="changeTab('programing')"
                class="cursor-pointer w-full hover:bg-p-lightRed hover:text-p-lightBlackisBrown"
                :class="{
                    'bg-p-lightBrown text-p-lightBlackisBrown':
                        TAB === 'programing',
                }"
            >
                Programing <span :class="{
                    'text-p-lightBlackisBrown':
                        TAB === 'programing',
                }">[{{ PROGRAMING_COUNT }}]</span>
            </button>
            <button
                @click="changeTab('other')"
                class="cursor-pointer w-full hover:bg-p-lightRed hover:text-p-lightBlackisBrown"
                :class="{
                    'bg-p-lightBrown text-p-lightBlackisBrown': TAB === 'other',
                }"
            >
                Other <span :class="{
                    'text-p-lightBlackisBrown':
                        TAB === 'other',
                }">[{{ OTHER_COUNT }}]</span>
            </button>
        </div>

        <!-- <div class="grid grid-cols-1 sm:grid-cols-2 2xl:grid-cols-3 self-center gap-8 w-10/12">
            <ProjectCard v-for="project in PROJECTS[TAB]" :key="project.title" :project="project" />
        </div> -->
        <div class="columns-1 sm:columns-2 2xl:columns-3 gap-8 w-10/12 mx-auto">
            <div v-for="project in PROJECTS[TAB]" :key="project.title" class="mb-8 break-inside-avoid">
                <ProjectCard :project="project" />
            </div>
        </div>
    </main>
</template>
