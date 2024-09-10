<script setup>
import { ref, onMounted, onUnmounted } from 'vue';
import { ChevronDoubleDownIcon, ChevronLeftIcon, ChevronRightIcon } from '@heroicons/vue/24/outline';

const recommendations = ref([
    {
        name: 'Walter Coan',
        recommendation: "I was Arthur's professor in the Software Factory course in 2024, where he was able to develop a web information system for event management aimed at people who like sports cars. The application was developed using the Vue.js framework and a Rest API with Spring Boot. In addition, Arthur regularly participates in study groups preparing for the Azure Fundamentals (AZ-900) and AWS Cloud Practitioner certification exams.",
        image: 'https://media.licdn.com/dms/image/v2/D4D03AQErQ2jR6dOEDQ/profile-displayphoto-shrink_200_200/profile-displayphoto-shrink_200_200/0/1689381096241?e=1731542400&v=beta&t=h3ZREAq_ymd0bYfWWxboo7Gt5-1WR2Fb2P-kA0ItAMg',
        link: 'https://www.linkedin.com/in/waltercoan/',
    },
    {
        name: 'Thiago Rodrigues',
        recommendation: "I worked with Arthur on several projects, and I certainly learned a lot from him. He is a very dedicated professional who strives to learn something new in every project. His knowledge of Laravel and Vue helped in the construction of complex pages and functionalities. If you are looking for a dedicated and talented professional, then you are definitely looking for Arthur.",
        image: 'https://media.licdn.com/dms/image/v2/D4D03AQHYW-SNX9D98A/profile-displayphoto-shrink_100_100/profile-displayphoto-shrink_100_100/0/1692387613005?e=1731542400&v=beta&t=SZt-eMm8AOyMWSL8hFIgljjZpArRKhbwDxdeGs5Jm_Y',
        link: 'https://www.linkedin.com/in/thiago-rodrigues-604947120/',
    },
    {
        name: 'Matheus Bittencourt',
        recommendation: "I had the opportunity to collaborate with Arthur on several projects, and I can affirm that I learned a lot from him. He is an extremely dedicated professional, always looking to acquire new knowledge in each task. His expertise in Laravel and Vue was fundamental to the development of web applications and complex functionalities on specific pages. If you are looking for a committed and talented professional, Arthur is undoubtedly the right person.",
        image: 'https://media.licdn.com/dms/image/v2/D4D03AQFlk9XesEYlnA/profile-displayphoto-shrink_100_100/profile-displayphoto-shrink_100_100/0/1700651831182?e=1731542400&v=beta&t=ZUKfc6D9NnquGCWN90TpsKY5GjJ2dNF1VCdG-1hPEig',
        link: 'https://www.linkedin.com/in/matheus-bittencourt-santos/',
    },
    {
        name: 'Giordano Gava',
        recommendation: "I study with Arthur at the university, and we have already done some group projects together. He has demonstrated a vast knowledge of programming, especially in Vue.js and Laravel. In addition, he is a very focused person and works very well in a team.",
        image: 'https://media.licdn.com/dms/image/v2/D4D03AQEh5fuznsKc7w/profile-displayphoto-shrink_100_100/profile-displayphoto-shrink_100_100/0/1689879356741?e=1731542400&v=beta&t=myUHEsr6ycuj0UNgHM-vNgkwHlID2d8BS270-xH3kok',
        link: 'https://www.linkedin.com/in/giordanogava/',
    },
]);

const currentSlide = ref(0);
let interval = null;

const nextSlide = () => {
    currentSlide.value = (currentSlide.value + 1) % recommendations.value.length;
};

const prevSlide = () => {
    currentSlide.value = (currentSlide.value - 1 + recommendations.value.length) % recommendations.value.length;
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
                            <div v-for="(recommendation, index) in recommendations" :key="index" class="w-full flex-shrink-0 px-14">
                                <div class="bg-white p-8 rounded-xl relative z-20">
                                    <a
                                        :href="recommendation.link"
                                        target="_blank"
                                        class="flex items-center justify-center space-x-2 hover:scale-110 duration-500 z-30"
                                    >
                                        <img :src="recommendation.image" class="rounded-full h-10 w-10" />
                                        <span class="text-xl font-bold tracking-tight text-gray-900">{{ recommendation.name }}</span>
                                    </a>
                                    <p class="mt-4 sm:text-lg leading-8 text-gray-600 text-center">{{ recommendation.recommendation }}</p>
                                </div>
                            </div>
                        </div>

                        <div class="absolute inset-0 flex justify-between items-center z-10 pointer-events-none">
                            <button @click="prevSlide" class="p-2 bg-gray-800 text-white rounded-full pointer-events-auto">
                                <ChevronLeftIcon class="h-6 w-6" />
                            </button>
                            <button @click="nextSlide" class="p-2 bg-gray-800 text-white rounded-full pointer-events-auto">
                                <ChevronRightIcon class="h-6 w-6" />
                            </button>
                        </div>
                    </div>
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
