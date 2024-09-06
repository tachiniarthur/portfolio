<script setup>
import { ChevronDoubleDownIcon } from '@heroicons/vue/24/outline';

</script>

<template>
    <section id="about">

        <div class="px-6 pt-14 lg:px-8">
            <div class="mx-auto max-w-2xl py-32 sm:py-48 lg:pt-56 lg:pb-44">
                <div class="flex flex-col justify-center text-center items-center">
                    <h2 class="text-4xl font-bold tracking-tight text-gray-900 sm:text-6xl mb-6">About me</h2>
                    <div class="flex flex-col lg:flex-row items-center lg:gap-8">
                        <p class="mt-6 text-lg leading-8 text-gray-600">I am 21 years old and a native of Joinville, Santa Catarina, where I have lived my whole life. I'm passionate about music of all genres and love binge-watching movies and series. I enjoy going to the gym, studying, and traveling. In my free time, I like exploring new hobbies, learning new things, and spending peaceful moments with my loved ones</p>
                        <img src="../assets/my-profile.svg" alt="Arthur Tachini" class="w-80 h-80 mt-6 lg:mt-0" />
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