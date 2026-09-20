<script setup lang="ts">
import { RouterLink, RouterView, useRoute } from "vue-router";
import { ref, onMounted } from "vue";

const selected = ref<string | null>(null);

const ROUTE = useRoute();

const isDark = ref(false);

function toggleDark() {
    isDark.value = !isDark.value;
    document.body.classList.toggle("dark", isDark.value);
    localStorage.setItem("theme", isDark.value ? "dark" : "light");
}

onMounted(() => {
    // Respect saved preference, fallback to system preference
    const saved = localStorage.getItem("theme");
    const prefersDark = window.matchMedia(
        "(prefers-color-scheme: dark)",
    ).matches;

    isDark.value = saved ? saved === "dark" : prefersDark;
    document.body.classList.toggle("dark", isDark.value);
});
</script>

<template>
    <div class="min-h-screen flex flex-col">
        <header
            
            class="p-2 flex justify-between text-pl-text dark:text-pd-text"
        >
            <div>
                <RouterLink
                    to="/"
                    class="relative inline-block group font-bold"
                    @mouseenter="selected = 'about'"
                    @mouseleave="selected = null"
                >
                    Aymane
                    <span
                        class="absolute left-0 -bottom-1 h-px w-full bg-pl-text dark:bg-pd-text origin-center scale-x-0 transition-transform duration-200 ease-out group-hover:scale-x-100"
                    ></span>
                </RouterLink>
            </div>
            <div class="flex gap-8">
                <nav v-if="ROUTE.path != '/'" class="flex items-center gap-8">
                    <RouterLink
                        to="/about"
                        class="relative inline-block group"
                        @mouseenter="selected = 'about'"
                        @mouseleave="selected = null"
                    >
                        about
                        <span
                            class="absolute left-0 -bottom-1 h-px w-full bg-pl-text dark:bg-pd-text origin-center scale-x-0 transition-transform duration-200 ease-out group-hover:scale-x-100"
                        ></span>
                    </RouterLink>
                    <RouterLink
                        to="/projects"
                        class="relative inline-block group"
                        @mouseenter="selected = 'projects'"
                        @mouseleave="selected = null"
                    >
                        projects
                        <span
                            class="absolute left-0 -bottom-1 h-px w-full bg-pl-text dark:bg-pd-text origin-center scale-x-0 transition-transform duration-200 ease-out group-hover:scale-x-100"
                        ></span>
                    </RouterLink>
                    <RouterLink
                        to="/sides"
                        class="relative inline-block group"
                        @mouseenter="selected = 'sides'"
                        @mouseleave="selected = null"
                    >
                        sides
                        <span
                            class="absolute left-0 -bottom-1 h-px w-full bg-pl-text dark:bg-pd-text origin-center scale-x-0 transition-transform duration-200 ease-out group-hover:scale-x-100"
                        ></span>
                    </RouterLink>
                </nav>
                <button
                    @click="toggleDark"
                    class="cursor-pointer text-pl-text dark:text-pd-text transition-colors"
                    aria-label="Toggle dark mode"
                >
                    <svg
                        v-if="isDark"
                        xmlns="http://www.w3.org/2000/svg"
                        viewBox="0 0 24 24"
                        fill="currentColor"
                        class="w-5 h-5"
                    >
                        <path
                            d="M12 3a9 9 0 1 0 9 9c0-.46-.04-.92-.1-1.36a5.4 5.4 0 0 1-7.54-7.54A9 9 0 0 0 12 3Z"
                        />
                    </svg>
                    <svg
                        v-else
                        xmlns="http://www.w3.org/2000/svg"
                        viewBox="0 0 24 24"
                        fill="currentColor"
                        class="w-5 h-5"
                    >
                        <path
                            d="M12 4V2m0 20v-2m8-8h2M2 12h2m13.66-6.66 1.41-1.41M4.93 19.07l1.41-1.41M18.36 18.36l1.41 1.41M4.93 4.93 6.34 6.34"
                            stroke="currentColor"
                            stroke-width="2"
                            stroke-linecap="round"
                            fill="none"
                        />
                        <circle cx="12" cy="12" r="5" />
                    </svg>
                </button>
            </div>
        </header>

        <!-- <RouterView class="py-8 flex-1" /> -->
        <RouterView class="py-8 flex-1" v-slot="{ Component }">
            <Transition
                enter-active-class="transition duration-200 ease-out"
                enter-from-class="opacity-0 translate-y-5"
                enter-to-class="opacity-100 translate-y-0"
                leave-active-class="transition duration-300 ease-in"
                leave-from-class="opacity-100 translate-y-0"
                leave-to-class="opacity-0 -translate-y-5"
                mode="out-in"
            >
                <component :is="Component" />
            </Transition>
        </RouterView>
        
    </div>
</template>
