<script setup lang="ts">
import { RouterLink, RouterView, useRoute } from "vue-router";
import { ref, watch, onMounted } from "vue";

const ROUTE = useRoute();

const isDark = ref(false);
const open = ref(false);

const links = [
    { to: "/about", label: "about" },
    { to: "/projects", label: "projects" },
    { to: "/sides", label: "sides" },
];

// close the burger menu on any navigation
watch(
    () => ROUTE.path,
    () => (open.value = false),
);

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
        <header class="sticky top-0 z-50 p-2 flex justify-between items-center text-pl-text dark:text-pd-text
               transition-colors duration-200"
            :class="open ? 'bg-transparent' : 'bg-pl-background dark:bg-pd-background'">
            <div>
                <RouterLink to="/" v-slot="{ isExactActive }" class="relative inline-block group font-bold">
                    Aymane
                    <span
                        class="absolute left-0 -bottom-1 h-px w-full bg-pl-text dark:bg-pd-text origin-center transition-transform duration-200 ease-out group-hover:scale-x-100"
                        :class="isExactActive ? 'scale-x-100' : 'scale-x-0'"></span>
                </RouterLink>
            </div>

            <div class="flex items-center gap-8">
                <!-- Desktop nav -->
                <nav v-if="ROUTE.path != '/'" class="hidden sm:flex items-center gap-8">
                    <RouterLink v-for="link in links" :key="link.to" :to="link.to" v-slot="{ isActive }"
                        class="relative inline-block group">
                        {{ link.label }}
                        <span
                            class="absolute left-0 -bottom-1 h-px w-full bg-pl-text dark:bg-pd-text origin-center transition-transform duration-200 ease-out group-hover:scale-x-100"
                            :class="isActive ? 'scale-x-100' : 'scale-x-0'"></span>
                    </RouterLink>
                </nav>

                <!-- Dark mode toggle -->
                <button @click="toggleDark" class="cursor-pointer text-pl-text dark:text-pd-text transition-colors"
                    aria-label="Toggle dark mode">
                    <svg v-if="isDark" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor"
                        class="w-5 h-5">
                        <path d="M12 3a9 9 0 1 0 9 9c0-.46-.04-.92-.1-1.36a5.4 5.4 0 0 1-7.54-7.54A9 9 0 0 0 12 3Z" />
                    </svg>
                    <svg v-else xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor"
                        class="w-5 h-5">
                        <path
                            d="M12 4V2m0 20v-2m8-8h2M2 12h2m13.66-6.66 1.41-1.41M4.93 19.07l1.41-1.41M18.36 18.36l1.41 1.41M4.93 4.93 6.34 6.34"
                            stroke="currentColor" stroke-width="2" stroke-linecap="round" fill="none" />
                        <circle cx="12" cy="12" r="5" />
                    </svg>
                </button>

                <!-- Burger button (mobile only) -->
                <button v-if="ROUTE.path != '/'" @click="open = !open" class="sm:hidden cursor-pointer"
                    aria-label="Toggle menu" :aria-expanded="open">
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor"
                        stroke-width="2" stroke-linecap="round" class="w-6 h-6">
                        <path v-if="!open" d="M4 6h16M4 12h16M4 18h16" />
                        <path v-else d="M6 6l12 12M18 6L6 18" />
                    </svg>
                </button>
            </div>
        </header>

        <!-- Mobile overlay menu -->
        <Transition enter-active-class="transition duration-200 ease-out" enter-from-class="opacity-0"
            enter-to-class="opacity-100" leave-active-class="transition duration-200 ease-in"
            leave-from-class="opacity-100" leave-to-class="opacity-0">
            <nav v-if="open" class="sm:hidden fixed inset-0 z-40 flex flex-col items-center justify-center gap-8 text-2xl
           bg-pl-background/80 dark:bg-pd-background/80 backdrop-blur-sm text-pl-text dark:text-pd-text">
                <RouterLink v-for="link in links" :key="link.to" :to="link.to"
                    active-class="underline underline-offset-8" @click="open = false">
                    {{ link.label }}
                </RouterLink>
            </nav>
        </Transition>

        <RouterView class="py-8 flex-1" v-slot="{ Component }">
            <Transition enter-active-class="transition duration-200 ease-out" enter-from-class="opacity-0 translate-y-5"
                enter-to-class="opacity-100 translate-y-0" leave-active-class="transition duration-300 ease-in"
                leave-from-class="opacity-100 translate-y-0" leave-to-class="opacity-0 -translate-y-5" mode="out-in">
                <component :is="Component" />
            </Transition>
        </RouterView>
    </div>
</template>
