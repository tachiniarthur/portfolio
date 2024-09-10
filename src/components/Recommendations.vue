<script setup>
import { ref, onMounted, onUnmounted } from 'vue';
import { ChevronDoubleDownIcon, ChevronLeftIcon, ChevronRightIcon } from '@heroicons/vue/24/outline';

const currentSlide = ref(0);
let interval = null;

const nextSlide = () => {
    currentSlide.value = (currentSlide.value + 1) % 4;
};

const prevSlide = () => {
    currentSlide.value = (currentSlide.value - 1 + 4) % 4;
};

const startAutoplay = () => {
    interval = setInterval(nextSlide, 10000);
};

const stopAutoplay = () => {
    if (interval) {
        clearInterval(interval);
    }
};

onMounted(() => {
    startAutoplay();
});

onUnmounted(() => {
    stopAutoplay();
});
</script>

<template>
    <section class="bg-custom" id="recommendations">
        <div class="mx-auto max-w-2xl py-32 sm:py-48 lg:py-48 px-8 md:px-0">
            <div class="flex flex-col justify-center items-center slide-animation">
                <h2 class="mb-14 text-4xl font-bold tracking-tight text-gray-900 sm:text-6xl">Recomendations</h2>

                <div class="relative w-full">
                    <div class="overflow-hidden relative">
                        <div
                            class="flex transition-transform duration-500 ease-in-out items-center"
                            :style="{ transform: `translateX(-${currentSlide * 100}%)` }"
                        >
                            <div class="w-full flex-shrink-0 px-14">
                                <div class="bg-white p-8 rounded-xl relative z-20">
                                    <a
                                        href="https://www.linkedin.com/in/waltercoan/"
                                        target="_blank"
                                        class="flex items-center justify-center space-x-2 hover:scale-110 duration-500 z-30"
                                        aria-label="Redirect to LinkedIn Walter Coan profile"
                                    >
                                        <img src="../assets/walter.svg" alt="Foto de usuário da recomendação" class="rounded-full h-10 w-10" />
                                        <span class="text-xl font-bold tracking-tight text-gray-900">Walter Coan</span>
                                    </a>
                                    <p class="mt-4 sm:text-lg leading-8 text-gray-600 text-center">I was Arthur's professor in the Software Factory course in 2024, where he was able to develop a web information system for event management aimed at people who like sports cars. The application was developed using the Vue.js framework and a Rest API with Spring Boot. In addition, Arthur regularly participates in study groups preparing for the Azure Fundamentals (AZ-900) and AWS Cloud Practitioner certification exams.</p>
                                </div>
                            </div>
                            <div class="w-full flex-shrink-0 px-14">
                                <div class="bg-white p-8 rounded-xl relative z-20">
                                    <a
                                        href="https://www.linkedin.com/in/thiago-rodrigues-604947120/"
                                        target="_blank"
                                        class="flex items-center justify-center space-x-2 hover:scale-110 duration-500 z-30"
                                        aria-label="Redirect to LinkedIn Thiago Rodrigues profile"
                                    >
                                        <img src="../assets/thiago.svg" alt="Foto de usuário da recomendação" class="rounded-full h-10 w-10" />
                                        <span class="text-xl font-bold tracking-tight text-gray-900">Thiago Rodrigues</span>
                                    </a>
                                    <p class="mt-4 sm:text-lg leading-8 text-gray-600 text-center">I worked with Arthur on several projects, and I certainly learned a lot from him. He is a very dedicated professional who strives to learn something new in every project. His knowledge of Laravel and Vue helped in the construction of complex pages and functionalities. If you are looking for a dedicated and talented professional, then you are definitely looking for Arthur.</p>
                                </div>
                            </div>
                            <div class="w-full flex-shrink-0 px-14">
                                <div class="bg-white p-8 rounded-xl relative z-20">
                                    <a
                                        href="https://www.linkedin.com/in/matheus-bittencourt-santos/"
                                        target="_blank"
                                        class="flex items-center justify-center space-x-2 hover:scale-110 duration-500 z-30"
                                        aria-label="Redirect to LinkedIn Matheus Bittencourt profile"
                                    >
                                        <img src="../assets/matheus.svg" alt="Foto de usuário da recomendação" class="rounded-full h-10 w-10" />
                                        <span class="text-xl font-bold tracking-tight text-gray-900">Matheus Bittencourt</span>
                                    </a>
                                    <p class="mt-4 sm:text-lg leading-8 text-gray-600 text-center">I had the opportunity to collaborate with Arthur on several projects, and I can affirm that I learned a lot from him. He is an extremely dedicated professional, always looking to acquire new knowledge in each task. His expertise in Laravel and Vue was fundamental to the development of web applications and complex functionalities on specific pages. If you are looking for a committed and talented professional, Arthur is undoubtedly the right person.</p>
                                </div>
                            </div>
                            
                            <div class="w-full flex-shrink-0 px-14">
                                <div class="bg-white p-8 rounded-xl relative z-20">
                                    <a
                                        href="https://www.linkedin.com/in/giordanogava/"
                                        target="_blank"
                                        class="flex items-center justify-center space-x-2 hover:scale-110 duration-500 z-30"
                                        aria-label="Redirect to LinkedIn Giordano Gava profile"
                                    >
                                        <img src="../assets/giordano.svg" alt="Foto de usuário da recomendação" class="rounded-full h-10 w-10" />
                                        <span class="text-xl font-bold tracking-tight text-gray-900">Giordano Gava</span>
                                    </a>
                                    <p class="mt-4 sm:text-lg leading-8 text-gray-600 text-center">I study with Arthur at the university, and we have already done some group projects together. He has demonstrated a vast knowledge of programming, especially in Vue.js and Laravel. In addition, he is a very focused person and works very well in a team.</p>
                                </div>
                            </div>
                        </div>

                        <div class="absolute inset-0 flex justify-between items-center z-10 pointer-events-none">
                            <button @click="prevSlide" class="p-2 bg-gray-800 text-white rounded-full pointer-events-auto" aria-label="Previous recommendation" title="Previous recommendation">
                                <ChevronLeftIcon class="h-6 w-6" />
                            </button>
                            <button @click="nextSlide" class="p-2 bg-gray-800 text-white rounded-full pointer-events-auto" aria-label="Next recommendation" title="Next recommendation">
                                <ChevronRightIcon class="h-6 w-6" />
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <div class="mx-auto max-w-2xl flex items-center justify-center">
            <a href="#contact" aria-label="Next section">
                <ChevronDoubleDownIcon class="h-8 w-8 animate-bounce relative z-50" aria-hidden="true" />
            </a>
        </div>
    </section>
</template>
