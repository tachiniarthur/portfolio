<script setup>
import { ref } from 'vue';
import { ChevronDoubleDownIcon } from '@heroicons/vue/24/outline';

const projects = ref([
    {
        title: 'Project 1',
        image: 'https://via.placeholder.com/500',
    },
    {
        title: 'Project 2',
        image: 'https://via.placeholder.com/500',
    },
]);
</script>

<template>
    <section id="projects">

        <div class="mx-auto max-w-2xl py-32 sm:py-48 lg:py-48 px-8 md:px-0">
            <div class="flex flex-col justify-center items-center slide-animation">
                <h2 class="mt-2 text-4xl font-bold tracking-tight text-gray-900 sm:text-6xl">Projects</h2>
                <div class="flex flex-col lg:flex-row items-center lg:gap-10 mt-6">
                    <div v-for="project in projects" class="flex flex-col items-center">
                        <h3 class="mb-2 text-2xl font-bold tracking-tight text-gray-900">{{ project.title }}</h3>
                        <img :src="project.image" />
                    </div>
                </div>
            </div>
        </div>

        <div class="mx-auto max-w-2xl flex items-center justify-center">
            <a href="#contact">
                <ChevronDoubleDownIcon class="h-8 w-8 animate-bounce relative z-50" aria-hidden="true" />
            </a>
        </div>

    </section>
</template>