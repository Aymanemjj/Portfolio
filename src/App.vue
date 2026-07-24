<script setup lang="ts">
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
    <div class="min-h-screen flex flex-col">
        <header
            class="border-2 border-p-lightBrown bg-p-lightBlackisBrown p-2 flex justify-center"
        >
            <nav class="flex gap-32 text-p-lightBrown font-bold">
                <RouterLink
                    class="hover:bg-p-lightRed hover:text-p-lightBlackisBrown p-2 [&.router-link-exact-active]:bg-p-lightBrown [&.router-link-exact-active]:text-p-lightBlackisBrown"
                    to="/"
                    >Home</RouterLink
                >
                <RouterLink
                    class="hover:bg-p-lightRed hover:text-p-lightBlackisBrown p-2 [&.router-link-exact-active]:bg-p-lightBrown [&.router-link-exact-active]:text-p-lightBlackisBrown"
                    to="/about"
                    >About</RouterLink
                >
                <RouterLink
                    class="hover:bg-p-lightRed hover:text-p-lightBlackisBrown p-2 [&.router-link-exact-active]:bg-p-lightBrown [&.router-link-exact-active]:text-p-lightBlackisBrown"
                    to="/projects"
                    >Projects</RouterLink
                >
            </nav>
        </header>

        <RouterView class="py-8 flex-1" />

        <!-- <footer class="border-2 border-p-lightBrown bg-p-lightBlackisBrown p-4 flex justify-center">
            <p class="text-p-lightBrown font-bold">By: <span class="font-normal">Mohamed Aymane Jaafouri</span></p>
        </footer> -->
    </div>
</template>
