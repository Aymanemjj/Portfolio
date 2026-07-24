<script setup lang="ts"></script>

<template>
    <main class="max-w-3xl mx-auto flex flex-col text-p-lightBrown gap-16 px-4">
        <!-- About Me -->
        <section class="flex flex-col gap-4">
            <b class="text-p-green text-2xl">About Me</b>
            <p>
                Hi! I'm Aymane, a full-stack Web Developer based in Morocco,
                interested in CS among other fields like design and 3d
                modeling
            </p>
        </section>

        <!-- Technologies -->
        <section class="flex flex-col gap-4">
            <b class="text-p-green text-2xl">Technologies</b>
            <div class="flex flex-col gap-3">
                <div class="flex gap-4">
                    <h3 class="text-p-lightRed text-xl w-40 shrink-0">Languages:</h3>
                    <p>TS / MySQL / C / JAVA / PHP</p>
                </div>
                <div class="flex gap-4">
                    <h3 class="text-p-lightRed text-xl w-40 shrink-0">Frameworks:</h3>
                    <p>VUE / REACT / LARAVEL</p>
                </div>
                <div class="flex gap-4">
                    <h3 class="text-p-lightRed text-xl w-40 shrink-0">Dev Tools:</h3>
                    <p>Docker / Git</p>
                </div>
                <div class="flex gap-4">
                    <h3 class="text-p-lightRed text-xl w-40 shrink-0">Other Tools:</h3>
                    <p>Blender / Photoshop / Illustrator / InDesign / Figma</p>
                </div>
            </div>
        </section>

        <!-- Resources -->
        <section class="flex flex-col gap-4">
            <b class="text-p-green text-2xl">Resources</b>
            <div class="flex flex-col gap-3">
                <div class="flex gap-4">
                    <h3 class="text-p-lightRed text-xl w-40 shrink-0">Email:</h3>
                    <a class="hover:underline"
                        href="mailto:aymanemj@proton.me"
                        target="_blank"
                        rel="noopener noreferrer"
                        >aymanemj@proton.me</a
                    >
                </div>
                <div class="flex gap-4">
                    <h3 class="text-p-lightRed text-xl w-40 shrink-0">LinkedIn:</h3>
                    <a class="hover:underline"
                        href="https://www.linkedin.com/in/mohamed-aymane-jaafouri-b83b17371/"
                        target="_blank"
                        rel="noopener noreferrer"
                        >Mohamed Aymane Jaafouri</a
                    >
                </div>
                <div class="flex gap-4">
                    <h3 class="text-p-lightRed text-xl w-40 shrink-0">GitHub:</h3>
                    <a class="hover:underline"
                        href="https://github.com/Aymanemjj"
                        target="_blank"
                        rel="noopener noreferrer"
                        >Aymanemjj</a
                    >
                </div>
                <div class="flex gap-4">
                    <h3 class="text-p-lightRed text-xl w-40 shrink-0">Ungenerated:</h3>
                    <a class="hover:underline"
                        href="https://www.ungenerated.io/artists/Mawkli"
                        target="_blank"
                        rel="noopener noreferrer"
                        >Mawkli</a
                    >
                </div>
                <div class="flex gap-4">
                    <h3 class="text-p-lightRed text-xl w-40 shrink-0">CV:</h3>
                    <a class="hover:underline"
                        href="/cv.pdf"
                        target="_blank"
                        rel="noopener noreferrer"
                        >CV</a
                    >
                </div>
            </div>
        </section>
    </main>
</template>