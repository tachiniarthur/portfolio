<script setup>
import { ChevronDoubleDownIcon } from '@heroicons/vue/24/outline';

</script>

<template>
    <section id="about">

        <div class="mx-auto max-w-2xl py-32 sm:py-48 lg:py-48 px-8 md:px-0">
            <div class="flex flex-col justify-center items-center slide-animation">
                <h2 class="mt-2 text-4xl font-bold tracking-tight text-gray-900 sm:text-6xl">About me</h2>
                <div class="flex flex-col lg:flex-row items-center lg:gap-10">
                    <p class="mt-6 text-md sm:text-lg leading-8 text-gray-600 text-center lg:text-end">I am 21 years old and a native of Joinville, Santa Catarina, where I have lived my whole life. I'm passionate about music of all genres and love binge-watching movies and series. I enjoy going to the gym, studying, and traveling. In my free time, I like exploring new hobbies, learning new things, and spending peaceful moments with my loved ones.</p>
                    <img src="../assets/my-profile.svg" alt="Arthur Tachini" class="w-80 h-80 mt-6 lg:mt-0" />
                </div>
            </div>
        </div>

        <div class="mx-auto max-w-2xl flex items-center justify-center">
            <a href="#skills">
                <ChevronDoubleDownIcon class="h-8 w-8 animate-bounce relative z-50" aria-hidden="true" />
            </a>
        </div>

    </section>
</template>