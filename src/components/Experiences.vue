<script setup>
import { BriefcaseIcon, CheckIcon, ChevronDoubleDownIcon } from '@heroicons/vue/24/outline';
</script>

<template>
    <section id="experiences">

        <div class="mx-auto max-w-2xl py-32 md:py-48 px-8 md:px-0">
            <div class="text-center slide-animation">

                <h2 class="mb-14 text-4xl font-bold tracking-tight text-gray-900 sm:text-6xl">Experiences</h2>

                <div class="space-y-8 relative before:absolute before:inset-0 before:ml-5 before:-translate-x-px md:before:mx-auto md:before:translate-x-0 before:h-full before:w-0.5 before:bg-gradient-to-b before:from-transparent before:via-slate-300 before:to-transparent">

                    <div class="relative flex items-center justify-between md:justify-normal md:odd:flex-row-reverse group">
                        <div class="flex items-center justify-center w-10 h-10 rounded-full border border-white bg-slate-300 text-gray-600 shadow shrink-0 md:order-1 md:group-odd:-translate-x-1/2 md:group-even:translate-x-1/2">
                            <BriefcaseIcon class="w-5 h-5" aria-hidden="true" />
                        </div>
                        <div class="w-[calc(100%-4rem)] md:w-[calc(50%-2.5rem)] bg-white p-4 rounded border border-slate-200 shadow hover:scale-105 duration-500">
                            <div class="flex items-center justify-between space-x-2 mb-2">
                                <span class="font-bold text-start text-sm text-gray-800">Fullstack Developer Junior - FACE Digital</span>
                                <span class="text-end text-xs text-gray-800">2024 - Present</span>
                            </div>
                            <div class="flex items-center">
                                <span class="text-start text-sm text-gray-600">Worked on various high-level web projects using technologies such as PHP, Laravel (SOLID, DDD), HTML, CSS, Sass, Bootstrap, JavaScript, Vue, MongoDB, Oracle, and Docker. Also trained and mentored junior team members in best development practices.</span>
                            </div>
                        </div>
                    </div>
            
                    <div class="relative flex items-center justify-between md:justify-normal md:odd:flex-row-reverse group is-active">
                        <div class="flex items-center justify-center w-10 h-10 rounded-full border border-white bg-slate-300 group-[.is-active]:bg-gray-800 text-gray-600 group-[.is-active]:text-gray-50 shadow shrink-0 md:order-1 md:group-odd:-translate-x-1/2 md:group-even:translate-x-1/2">
                            <CheckIcon class="w-5 h-5" aria-hidden="true" />
                        </div>
                        <div class="w-[calc(100%-4rem)] md:w-[calc(50%-2.5rem)] bg-white p-4 rounded border border-slate-200 shadow hover:scale-105 duration-500">
                            <div class="flex items-center justify-between space-x-2 mb-2">
                                <span class="font-bold text-start text-sm text-gray-800">Trainee Developer - FACE Digital</span>
                                <span class="text-end text-xs text-gray-800">2022 - 2024</span>
                            </div>
                            <div class="flex items-center">
                                <span class="text-start text-sm text-gray-600">Developed and maintained various web projects using PHP, Laravel, HTML, CSS, Sass, Bootstrap, JavaScript, and Docker. Provided guidance and training to junior team members in development techniques.</span>
                            </div>
                        </div>
                    </div>

                </div>

            </div>
        </div>

        <div class="mx-auto max-w-2xl flex items-center justify-center">
            <a href="#projects" aria-label="Next section">
                <ChevronDoubleDownIcon class="h-8 w-8 animate-bounce relative z-50" aria-hidden="true" />
            </a>
        </div>

    </section>
</template>

