<script setup>
import { ref } from 'vue';
import { ChevronDoubleDownIcon } from '@heroicons/vue/24/outline';

const skills = ref([
    'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/html5/html5-original-wordmark.svg',
    'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/css3/css3-original-wordmark.svg',  
    'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/sass/sass-original.svg',
    'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/bootstrap/bootstrap-original-wordmark.svg',
    'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/tailwindcss/tailwindcss-original.svg',
    'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/javascript/javascript-original.svg',
    'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/jquery/jquery-original-wordmark.svg',
    'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/vuejs/vuejs-original-wordmark.svg',
    'https://raw.githubusercontent.com/innocenzi/awesome-inertiajs/master/assets/logo.svg?sanitize=true',
    'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/php/php-original.svg',
    'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/laravel/laravel-original-wordmark.svg',
    'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/codeigniter/codeigniter-plain-wordmark.svg',
    'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/java/java-original-wordmark.svg',
    'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/spring/spring-original-wordmark.svg',
    'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/python/python-original-wordmark.svg',
    'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/mysql/mysql-original-wordmark.svg',
    'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/mariadb/mariadb-original-wordmark.svg',
    'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/mongodb/mongodb-original-wordmark.svg',
    'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/oracle/oracle-original.svg',
    'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/docker/docker-original-wordmark.svg',
    'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/git/git-original-wordmark.svg',
    'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/github/github-original-wordmark.svg',
    'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/gitlab/gitlab-original-wordmark.svg',
    'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/bitbucket/bitbucket-original-wordmark.svg',
]);

</script>

<template>
    <section class="bg-custom" id="skills">

        <div class="mx-auto max-w-2xl py-32 sm:py-48 lg:py-48 px-8 md:px-0">
            <div class="flex flex-col justify-center text-center items-center slide-animation">
                <h2 class="mb-14 text-4xl font-bold tracking-tight text-gray-900 sm:text-6xl">Skills</h2>
                <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-x-10 gap-y-6 lg:gap-y-6">
                    <div class="bg-white shadow-lg rounded-lg p-4 hover:scale-110 duration-500" v-for="skill in skills">
                        <img :src="skill" class="w-16 h-16" />
                    </div>
                </div>
            </div>
        </div>

        <div class="mx-auto max-w-2xl flex items-center justify-center">
            <a href="#experiences">
                <ChevronDoubleDownIcon class="h-8 w-8 animate-bounce relative z-50" aria-hidden="true" />
            </a>
        </div>

    </section>
</template>