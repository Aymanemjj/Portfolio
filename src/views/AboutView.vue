<script setup lang="ts"></script>

<template>
    <main class="max-w-4xl mx-auto flex flex-col gap-16 px-4">
        <!-- about me -->
        <section class="flex gap-4">
            <div class="h-32 sm:h-64 lg:h-80 shrink-0">
                <img
                    src="@/assets/pfp.webp"
                    alt="pfp"
                    class="h-full w-auto object-contain"
                />
            </div>
            <div class="flex flex-col gap-4 text-left justify-end">
                <b class="text-pl-primary dark:text-pd-primary text-2xl"
                    >About me</b
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
                >Technologies</b
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
                        data & AI:
                    </h3>
                    <p>pandas / numpy / matplotlib / seaborn / schikit_learn</p>

                    <!--                     <p>MachineLearning (Classification, Regression, Clustering) / Deep Learning (TensorFlow, Keras, PyTorch) / NLP / Computer Vision / Analyse de donnees / Evaluation de mode LES</p>
 -->
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
                >Experience</b
            >
            <div class="flex flex-col gap-3 text-pl-text dark:text-pd-text">
                <div class="flex gap-4">
                    <h3
                        class="text-pl-secondary dark:text-pd-secondary text-xl shrink-0"
                    >
                        <a
                            href="https://www.yool.education/"
                            class="hover:underline"
                            >Yool Education:</a
                        >
                    </h3>
                    <div class="space-y-2">
                        <ul class="list-disc pl-5 space-y-1">
                            <li>
                                <span class="font-bold">Architecture:</span>
                                Solo-designed a scalable platform integrating 7
                                platforms, starting from the UML diagrams, with
                                a structure that makes adding more
                                straightforward.
                            </li>
                            <li>
                                <span class="font-bold"
                                    >Full-stack development:</span
                                >
                                Built the React.js front office and Laravel 11
                                back office from scratch.
                            </li>
                            <li>
                                <span class="font-bold"
                                    >Gamification and deployment:</span
                                >
                                Implemented background jobs for points,
                                achievements, and leaderboard snapshots, and
                                Dockerized the entire application.
                            </li>
                            <li>
                                <span class="font-bold underline">Technologies:</span>
                                TypeScript / PHP / Laravel / React.js / Redis /
                                Docker
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>

        <!-- resources -->
        <section class="flex flex-col gap-4">
            <b class="text-pl-primary dark:text-pd-primary text-2xl"
                >Resources</b
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
