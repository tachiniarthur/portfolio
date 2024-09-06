<script setup>
import { BriefcaseIcon, CheckIcon, ChevronDoubleDownIcon } from '@heroicons/vue/24/outline';
</script>

<template>
    <section id="experiences">

        <div class="px-6 pt-14 lg:px-8">
            <div class="mx-auto max-w-2xl py-32 sm:py-48 lg:pt-56 lg:pb-44">
                <div class="text-center">

                    <h1 class="mb-14 text-4xl font-bold tracking-tight text-gray-900 sm:text-6xl">Experiences</h1>

                    <div class="space-y-8 relative before:absolute before:inset-0 before:ml-5 before:-translate-x-px md:before:mx-auto md:before:translate-x-0 before:h-full before:w-0.5 before:bg-gradient-to-b before:from-transparent before:via-slate-300 before:to-transparent">

                        <div class="relative flex items-center justify-between md:justify-normal md:odd:flex-row-reverse group">
                            <div class="flex items-center justify-center w-10 h-10 rounded-full border border-white bg-slate-300 text-gray-600 shadow shrink-0 md:order-1 md:group-odd:-translate-x-1/2 md:group-even:translate-x-1/2">
                                <BriefcaseIcon class="w-5 h-5" aria-hidden="true" />
                            </div>
                            <div class="w-[calc(100%-4rem)] md:w-[calc(50%-2.5rem)] bg-white p-4 rounded border border-slate-200 shadow">
                                <div class="flex items-center justify-between space-x-2 mb-2">
                                    <span class="font-bold text-start text-sm text-gray-800">Fullstack Developer Junior</span>
                                    <span class="text-end text-sm text-blue-500">2024 - Present</span>
                                </div>
                                <div class="flex items-center">
                                    <span class="text-start text-sm text-gray-600">Worked on various high-level web projects using technologies such as PHP, Laravel (SOLID, DDD), HTML, CSS, Sass, Bootstrap, JavaScript, Vue, MongoDB, Oracle, and Docker. Also trained and mentored junior team members in best development practices.</span>
                                </div>
                            </div>
                        </div>
                
                        <div class="relative flex items-center justify-between md:justify-normal md:odd:flex-row-reverse group is-active">
                            <div class="flex items-center justify-center w-10 h-10 rounded-full border border-white bg-slate-300 group-[.is-active]:bg-blue-500 text-gray-600 group-[.is-active]:text-blue-50 shadow shrink-0 md:order-1 md:group-odd:-translate-x-1/2 md:group-even:translate-x-1/2">
                                <CheckIcon class="w-5 h-5" aria-hidden="true" />
                            </div>
                            <div class="w-[calc(100%-4rem)] md:w-[calc(50%-2.5rem)] bg-white p-4 rounded border border-slate-200 shadow">
                                <div class="flex items-center justify-between space-x-2 mb-2">
                                    <span class="font-bold text-start text-sm text-gray-800">Trainee Developer</span>
                                    <span class="text-end text-sm text-blue-500">2022 - 2024</span>
                                </div>
                                <div class="flex items-center">
                                    <span class="text-start text-sm text-gray-600">Developed and maintained various web projects using PHP, Laravel, HTML, CSS, Sass, Bootstrap, JavaScript, and Docker. Provided guidance and training to junior team members in development techniques.</span>
                                </div>
                            </div>
                        </div>

                    </div>

                </div>
            </div>
        </div>

        <div class="mx-auto max-w-2xl flex items-center justify-center">
            <a href="#experiences">
                <ChevronDoubleDownIcon class="h-8 w-8 animate-bounce" aria-hidden="true" />
            </a>
        </div>

    </section>
</template>

