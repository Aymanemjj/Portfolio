<script setup lang="ts">
import { ref, watch } from "vue";

const selected = ref<string | null>(null);
const displayText = ref("");

let timeoutId: ReturnType<typeof setTimeout> | null = null;

function clearPendingTimeout() {
    if (timeoutId) {
        clearTimeout(timeoutId);
        timeoutId = null;
    }
}

function typeText(target: string, onDone?: () => void) {
    clearPendingTimeout();

    function step(i: number) {
        displayText.value = target.slice(0, i);
        if (i < target.length) {
            timeoutId = setTimeout(() => step(i + 1), 60);
        } else {
            onDone?.();
        }
    }
    step(0);
}

function eraseText(onDone?: () => void) {
    clearPendingTimeout();

    function step(i: number) {
        displayText.value = displayText.value.slice(0, i);
        if (i > 0) {
            timeoutId = setTimeout(() => step(i - 1), 30);
        } else {
            onDone?.();
        }
    }
    step(displayText.value.length);
}

watch(selected, (newVal) => {
    if (newVal) {
        eraseText(() => typeText(newVal));
    } else {
        eraseText();
    }
});
</script>
<template>
    <main class="flex justify-center items-center">
        <div class="p-4 flex sm:flex-row flex-col gap-4 bg-pl-ascent dark:bg-pd-ascent xl:w-2/3">
            <div class="sm:h-64 lg:h-80 xl:h-96 shrink-0">
                <img src="@/assets/cat.gif" alt="cat" class="h-full w-auto object-contain text-pl-text dark:text-pd-text"/>
            </div>
            <div class="w-full  p-2 flex flex-col justify-between items-center gap-4">
                <div class="w-full text-left">
                    <h1 class="font-bold text-3xl text-pl-primary dark:text-pd-primary">Hallo!</h1>
                    <h2 class="text-pl-text dark:text-pd-text font-thin">
                        I am <span class="font-bold">Mohamed Aymane Jaafouri</span>, a full-stack web developer <span class="font-bold text-pl-primary dark:text-pd-primary underline">based in Morocco</span>, interested in cs among other fields like design and 3d modeling .
                    </h2>
                </div>
                <div class="w-full xl:w-2/3 flex flex-col  gap-8">
                    <div class="text-pl-secondary dark:text-pd-secondary font-bold flex justify-center text-2xl">
                        <b>&gt; cd ~/</b>
                        <b>
                            <span>{{ displayText }}</span>
                            <span v-if="!displayText" class="animate-pulse">_</span>
                            <span v-else class="animate-pulse">|</span>
                        </b>
                    </div>
                    <div class="w-full flex items-center justify-between text-pl-text dark:text-pd-text">
                        <RouterLink
                            to="/about"
                            class="relative inline-block text-pl-secondary dark:text-pd-secondary group"
                            @mouseenter="selected = 'about'"
                            @mouseleave="selected = null"
                        >
                            about
                            <span
                                class="absolute left-0 -bottom-1 h-px w-full bg-pl-secondary dark:bg-pd-secondary origin-center scale-x-0 transition-transform duration-200 ease-out group-hover:scale-x-100"
                            ></span>
                        </RouterLink>
                        <RouterLink
                            to="/projects"
                            class="relative inline-block text-pl-secondary dark:text-pd-secondary group"
                            @mouseenter="selected = 'projects'"
                            @mouseleave="selected = null"
                        >
                            projects
                            <span
                                class="absolute left-0 -bottom-1 h-px w-full bg-pl-secondary dark:bg-pd-secondary origin-center scale-x-0 transition-transform duration-200 ease-out group-hover:scale-x-100"
                            ></span>
                        </RouterLink>
                        <RouterLink
                            to="/sides"
                            class="relative inline-block text-pl-secondary dark:text-pd-secondary group"
                            @mouseenter="selected = 'sides'"
                            @mouseleave="selected = null"
                        >
                            sides
                            <span
                                class="absolute left-0 -bottom-1 h-px w-full bg-pl-secondary dark:bg-pd-secondary origin-center scale-x-0 transition-transform duration-200 ease-out group-hover:scale-x-100"
                            ></span>
                        </RouterLink>
                    </div>
                </div>
            </div>
        </div>
    </main>
</template>
