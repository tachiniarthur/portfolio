<script setup>
import { ChevronDoubleDownIcon } from '@heroicons/vue/24/outline';
</script>

<template>
    <section class="bg-custom" id="home">

        <div class="mx-auto max-w-2xl py-32 sm:py-48 lg:py-48 px-8 md:px-0">
            <div class="text-center">
                <p class="text-xl font-bold tracking-tight text-gray-800 sm:text-2xl">Fullstack Developer</p>
                <h1 class="mt-2 text-4xl font-bold tracking-tight text-gray-900 sm:text-6xl">Hello, I'm Arthur Tachini</h1>
                <p class="mt-6 text-md sm:text-lg leading-8 text-gray-600">
                    I'm a fullstack developer with a passion for building beautiful and functional websites. I specialize in creating responsive and user-friendly web applications using modern technologies.
                </p>
            </div>
        </div>

        <div class="mx-auto max-w-2xl flex items-center justify-center">
            <a href="#about" aria-label="Next section">
                <ChevronDoubleDownIcon class="h-8 w-8 animate-bounce relative z-50" aria-hidden="true" />
            </a>
        </div>

    </section>
</template>