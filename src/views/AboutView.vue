<script setup lang="ts"></script>

<template>
    <main class="max-w-4xl mx-auto flex flex-col gap-16 px-4">
        <!-- about me -->
        <section class="flex gap-4">
            <div class="h-32 sm:h-64 lg:h-80 shrink-0">
                <img
                    src="@/assets/pfp.png"
                    alt="pfp"
                    class="h-full w-auto object-contain"
                />
            </div>
            <div class="flex flex-col gap-4 text-left justify-end">
                <b class="text-pl-primary dark:text-pd-primary text-2xl"
                    >about me</b
                >
                <p class="text-pl-text dark:text-pd-text">
                    hi! i'm Aymane, a full-stack web developer based in morocco,
                    interested in cs among other fields like design and 3d
                    modeling.
                </p>
            </div>
        </section>

        <!-- technologies -->
        <section class="flex flex-col gap-4">
            <b class="text-pl-primary dark:text-pd-primary text-2xl"
                >technologies</b
            >
            <div class="flex flex-col gap-3 text-pl-text dark:text-pd-text">
                <div class="flex gap-4">
                    <h3
                        class="text-pl-secondary dark:text-pd-secondary text-xl w-40 shrink-0"
                    >
                        languages:
                    </h3>
                    <p>ts / python / php / golang / c</p>
                </div>
                <div class="flex gap-4">
                    <h3
                        class="text-pl-secondary dark:text-pd-secondary text-xl w-40 shrink-0"
                    >
                        frameworks:
                    </h3>
                    <p>vue_js / react_js / laravel</p>
                </div>
                <div class="flex gap-4">
                    <h3
                        class="text-pl-secondary dark:text-pd-secondary text-xl w-40 shrink-0"
                    >
                        databases:
                    </h3>
                    <p>mysql / postgrese_sql / redis</p>
                </div>
                <div class="flex gap-4">
                    <h3
                        class="text-pl-secondary dark:text-pd-secondary text-xl w-40 shrink-0"
                    >
                        data & ml:
                    </h3>
                    <p>pandas / numpy / matplotlib / seaborn / schikit_learn</p>
                </div>
                <div class="flex gap-4">
                    <h3
                        class="text-pl-secondary dark:text-pd-secondary text-xl w-40 shrink-0"
                    >
                        dev tools:
                    </h3>
                    <p>docker / git / airflow / linux</p>
                </div>
                <div class="flex gap-4">
                    <h3
                        class="text-pl-secondary dark:text-pd-secondary text-xl w-40 shrink-0"
                    >
                        other tools:
                    </h3>
                    <p>blender / photoshop / illustrator / indesign / figma</p>
                </div>
            </div>
        </section>
        <!-- Experience -->

        <section class="flex flex-col gap-4">
            <b class="text-pl-primary dark:text-pd-primary text-2xl"
                >experience</b
            >
            <div class="flex flex-col gap-3 text-pl-text dark:text-pd-text">
                <div class="flex gap-4">
                    <h3
                        class="text-pl-secondary dark:text-pd-secondary text-xl shrink-0"
                    >
                        <a
                            href="https://www.yool.education/"
                            class="hover:underline"
                            >yool education:</a
                        >
                    </h3>
                    <div>
                        <p>
                            2 month long intrenship, working on a real
                            production level project, of a centralized
                            gamification inbetween a diverse collection of other
                            platforms.
                        </p>
                        <p><span class="underline">technologies:</span> ts/ php / laravel / react_js / redis / docker</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- resources -->
        <section class="flex flex-col gap-4">
            <b class="text-pl-primary dark:text-pd-primary text-2xl"
                >resources</b
            >
            <div class="flex flex-col gap-3 text-pl-text dark:text-pd-text">
                <div class="flex gap-4">
                    <h3
                        class="text-pl-secondary dark:text-pd-secondary text-xl w-40 shrink-0"
                    >
                        email:
                    </h3>
                    <a
                        class="hover:underline"
                        href="mailto:aymanemj@proton.me"
                        target="_blank"
                        rel="noopener noreferrer"
                        >aymanemj@proton.me</a
                    >
                </div>
                <div class="flex gap-4">
                    <h3
                        class="text-pl-secondary dark:text-pd-secondary text-xl w-40 shrink-0"
                    >
                        linkedin:
                    </h3>
                    <a
                        class="hover:underline"
                        href="https://www.linkedin.com/in/mohamed-aymane-jaafouri-b83b17371/"
                        target="_blank"
                        rel="noopener noreferrer"
                        >mohamed aymane jaafouri</a
                    >
                </div>
                <div class="flex gap-4">
                    <h3
                        class="text-pl-secondary dark:text-pd-secondary text-xl w-40 shrink-0"
                    >
                        github:
                    </h3>
                    <a
                        class="hover:underline"
                        href="https://github.com/aymanemjj"
                        target="_blank"
                        rel="noopener noreferrer"
                        >aymanemjj</a
                    >
                </div>
                <div class="flex gap-4">
                    <h3
                        class="text-pl-secondary dark:text-pd-secondary text-xl w-40 shrink-0"
                    >
                        cara:
                    </h3>
                    <a
                        class="hover:underline"
                        href="https://cara.app/mawkli"
                        target="_blank"
                        rel="noopener noreferrer"
                        >mawkli</a
                    >
                </div>
                <div class="flex gap-4">
                    <h3
                        class="text-pl-secondary dark:text-pd-secondary text-xl w-40 shrink-0"
                    >
                        cv:
                    </h3>
                    <a
                        class="hover:underline"
                        href="/cv.pdf"
                        target="_blank"
                        rel="noopener noreferrer"
                        >cv</a
                    >
                </div>
            </div>
        </section>
    </main>
</template>
