<script setup>
import Header from './components/Header.vue';
import About from './components/About.vue';
import Skills from './components/Skills.vue';
import Experiences from './components/Experiences.vue';
import Projects from './components/Projects.vue';
import Contact from './components/Contact.vue';

import { ChevronDoubleDownIcon } from '@heroicons/vue/24/outline';
</script>

<template>
    <Header />
    
    <section class="bg-custom">
        <div class="px-6 pt-14 lg:px-8">
            <div class="mx-auto max-w-2xl py-32 sm:py-48 lg:pt-48 lg:pb-44">
                <div class="text-center">
                    <p class="text-xl font-bold tracking-tight text-gray-800 sm:text-3xl">Fullstack Developer</p>
                    <h1 class="mt-2 text-4xl font-bold tracking-tight text-gray-900 sm:text-6xl">Hello, I'm Arthur Tachini</h1>
                    <p class="mt-6 text-lg leading-8 text-gray-600">
                        I'm a fullstack developer with a passion for building beautiful and functional websites. I specialize in creating responsive and user-friendly web applications using modern technologies.
                    </p>
                </div>
            </div>
        </div>
        <div class="mx-auto max-w-2xl flex items-center justify-center pb-20">
            <a href="#about">
                <ChevronDoubleDownIcon class="h-8 w-8 animate-bounce" aria-hidden="true" />
            </a>
        </div>
    </section>

    <About />
    <Skills />
    <Experiences />
    <Projects />
    <Contact />

    <footer class="bg-gray-800 text-white py-8 text-center">
        <p class="text-sm">&copy; 2021 Arthur Tachini. All rights reserved.</p>
    </footer>
</template>

<style>
.bg-custom {
    background: linear-gradient(to right, rgba(245, 245, 245, 0.7), rgba(245, 245, 245, 0.7)), url(./assets/common-bg.svg);
    background-size: cover;
    background-position: center;
}

html {
    scroll-behavior: smooth;
}

@keyframes appear {
    from {
        opacity: 0;
        transform: translateX(-100px);
    }
    to {
        opacity: 1;
        transform: translateX(0px);
    }
}

section:not(:first-of-type) {
    animation: appear 1s;
    animation-timeline: view();
    animation-range: entry 30% cover 40%;
}
</style>