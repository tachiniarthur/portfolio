<script setup>
import { ref } from 'vue';
import { ChevronDoubleDownIcon, ChevronLeftIcon, ChevronRightIcon } from '@heroicons/vue/24/outline';

const recommendations = ref([
  {
    name: 'Walter Coan',
    recommendation: 'Fui professor do Arthur na disciplina de Fábrica de Software em 2024 onde ele foi capaz de desenvolver um sistema de informação Web para o gerenciamento de eventos direcionado para pessoas que gostam de carros esportivos. A aplicação foi desenvolvida utilizando o framework Vue.js e uma API Rest com o Spring Boot. Além disso, Arthur participa regulamente dos grupos de estudo para preparação para as provas de certificação Azure Fundamentals (AZ-900) e AWS Cloud Practitioner.',
    image: 'https://media.licdn.com/dms/image/v2/D4D03AQErQ2jR6dOEDQ/profile-displayphoto-shrink_200_200/profile-displayphoto-shrink_200_200/0/1689381096241?e=1731542400&v=beta&t=h3ZREAq_ymd0bYfWWxboo7Gt5-1WR2Fb2P-kA0ItAMg',
    link: 'https://www.linkedin.com/in/waltercoan/'
  },
  {
    name: 'Thiago Rodrigues',
    recommendation: 'Trabalhei com o Arthur em alguns projetos, e com certeza pude aprender muito com ele, é um profissional muito dedicado, que busca aprender algo novo em cada projeto. Seu conhecimento em Laravel e Vue auxiliaram para a contrução de páginas e funcionalidades complexas. Para quem busca um profissional dedicado e talentoso, então com certeza está em busca do Arthur.',
    image: 'https://media.licdn.com/dms/image/v2/D4D03AQHYW-SNX9D98A/profile-displayphoto-shrink_100_100/profile-displayphoto-shrink_100_100/0/1692387613005?e=1731542400&v=beta&t=SZt-eMm8AOyMWSL8hFIgljjZpArRKhbwDxdeGs5Jm_Y',
    link: 'https://www.linkedin.com/in/thiago-rodrigues-604947120/'
  },
  {
    name: 'Matheus Bittencourt',
    recommendation: 'Tive a oportunidade de colaborar com o Arthur em diversos projetos e posso afirmar que aprendi bastante com ele. Ele é um profissional extremamente dedicado, sempre buscando adquirir novos conhecimentos em cada tarefa. Seu domínio de Laravel e Vue foi fundamental para o desenvolvimento de aplicações web e funcionalidades complexas em páginas específicas. Se você está procurando um profissional comprometido e talentoso, o Arthur é, sem dúvida, a pessoa certa.',
    image: 'https://media.licdn.com/dms/image/v2/D4D03AQFlk9XesEYlnA/profile-displayphoto-shrink_100_100/profile-displayphoto-shrink_100_100/0/1700651831182?e=1731542400&v=beta&t=ZUKfc6D9NnquGCWN90TpsKY5GjJ2dNF1VCdG-1hPEig',
    link: 'https://www.linkedin.com/in/matheus-bittencourt-santos/'
  }
]);

const currentSlide = ref(0);

const nextSlide = () => {
  currentSlide.value = (currentSlide.value + 1) % recommendations.value.length;
};

const prevSlide = () => {
  currentSlide.value =
    (currentSlide.value - 1 + recommendations.value.length) % recommendations.value.length;
};
</script>

<template>
  <section class="bg-custom" id="recommendations">

    <div class="mx-auto max-w-2xl py-32 sm:py-48 lg:py-48 px-8 md:px-0">
        <div class="flex flex-col justify-center items-center slide-animation">
            <h2 class="mt-2 text-4xl font-bold tracking-tight text-gray-900 sm:text-6xl">Recomendations</h2>

            <div class="relative w-full mt-6 px-10">
            <div class="overflow-hidden">
                <div class="flex transition-transform duration-500 ease-in-out shadow-lg"
                :style="{ transform: `translateX(-${currentSlide * 100}%)` }">
                <div v-for="(recommendation, index) in recommendations" :key="index"
                    class="w-full flex-shrink-0 px-4">
                    <div class="bg-white p-8 rounded-xl">
                      <a :href="recommendation.link" class="flex items-center justify-center space-x-2 hover:scale-110 duration-500 z-100">
                          <img :src="recommendation.image" class="rounded-full h-10 w-10" >
                          <span class="text-xl font-bold tracking-tight text-gray-900">{{ recommendation.name }}</span>
                      </a>
                      <p class="mt-4 sm:text-lg leading-8 text-gray-600 text-center">{{ recommendation.recommendation }}</p>
                    </div>
                </div>
                </div>
            </div>
                <div class="absolute inset-0 flex justify-between items-center">
                    <button @click="prevSlide" class="p-2 bg-gray-800 text-white rounded-full">
                        <ChevronLeftIcon class="h-6 w-6" />
                    </button>
                    <button @click="nextSlide" class="p-2 bg-gray-800 text-white rounded-full">
                        <ChevronRightIcon class="h-6 w-6" />
                    </button>
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

<style scoped>
.slide-animation {
  overflow: hidden;
}
</style>
