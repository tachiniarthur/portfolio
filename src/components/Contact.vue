<script setup>
import { ref } from 'vue';
import emailjs from 'emailjs-com';
import { ExclamationCircleIcon, CheckCircleIcon, XMarkIcon } from '@heroicons/vue/24/outline';

const name = ref('');
const email = ref('');
const message = ref('');
const isLoading = ref(false);
const feedback = ref(false);
const feedbackTitle = ref('');
const feedbackMessage = ref('');
const feedbackColor = ref('bg-red-100');
const feedbackBorderColor = ref('border-red-500');

const sendEmail = (e) => {
    feedback.value = false;
    isLoading.value = true;
    e.preventDefault();

    if (!name.value || !email.value || !message.value) {
        setFeedback('Please fill in all fields.', 'error');
        isLoading.value = false;
        return;
    }

    const templateParams = {
        from_name: name.value,
        from_email: email.value,
        message: message.value,
    };

    emailjs
        .send(import.meta.env.VITE_SERVICE_ID, import.meta.env.VITE_TEMPLATE_ID, templateParams, import.meta.env.VITE_USER_ID)
        .then(
        (response) => {
            if (response.status == 200) {
                setFeedback('Email sent successfully!', 'success');
                name.value = '';
                email.value = '';
                message.value = '';
            } else {
                setFeedback('Failed to send email. Please try again.', 'error');
            }
        },
        (error) => {
            console.error('Erro ao enviar email:', error);
            setFeedback('An error occurred while sending the email. Please try again.', 'error');
        }
    )
    .finally(() => {
        isLoading.value = false;
    });
};

const setFeedback = (message, type) => {
    feedback.value = true;
    feedbackMessage.value = message;
    feedbackTitle.value = type == 'success' ? 'Success!' : 'Error!';
    feedbackColor.value = type == 'success' ? 'bg-green-100' : 'bg-red-100';
    feedbackBorderColor.value = type == 'success' ? 'border-green-500' : 'border-red-500';
};
</script>

<template>
    <section id="contact">

        <div class="mx-auto max-w-2xl py-32 md:py-48 px-8 md:px-0 relative">
            <div class="flex flex-col justify-center items-center slide-animation">
                <h2 class="mb-14 text-4xl font-bold tracking-tight text-gray-900 sm:text-6xl">Contact me</h2>
                <div class="rounded-lg p-8 flex flex-col items-center w-full bg-[#F6F6F6] shadow-lg">
                    <form :class="{ 'pointer-events-none opacity-60': isLoading }" action="#" method="post" class="min-w-full">
                        <div v-if="feedback" :class="`${feedbackColor} border-t-4 ${feedbackBorderColor} rounded-b text-gray-900 px-4 py-3 shadow-md mb-5 animate-slide-in-left`" role="alert">
                            <div class="flex">
                                <div class="py-1">
                                    <CheckCircleIcon v-if="feedbackTitle == 'Success!'" class="h-10 w-10 text-green-500 mr-4" />
                                    <ExclamationCircleIcon v-if="feedbackTitle == 'Error!'" class="h-10 w-10 text-red-500 mr-4" />
                                </div>
                                <div class="w-full">
                                    <div class="flex items-center justify-between">
                                        <p class="font-bold">{{ feedbackTitle }}</p>
                                        <button type="button" class="text-gray-900 hover:text-gray-800 hover:scale-110 duration-500" aria-label="Close alert" title="Close alert" @click="feedback = false" >
                                            <XMarkIcon class="h-6 w-6" />
                                        </button>
                                    </div>
                                    <p class="text-sm">{{ feedbackMessage }}</p>
                                </div>
                            </div>
                        </div>
                        <div class="mb-5">
                            <label for="name" class="block mb-2 text-sm font-medium text-gray-900">Your name</label>
                            <input type="text" v-model="name" id="name" class="bg-white border border-gray-300 text-gray-900 text-sm rounded-lg block w-full p-2.5" placeholder="John Doe" autocomplete />
                        </div>
                        <div class="mb-5">
                            <label for="email" class="block mb-2 text-sm font-medium text-gray-900">Your email</label>
                            <input type="email" v-model="email" id="email" class="bg-white border border-gray-300 text-gray-900 text-sm rounded-lg block w-full p-2.5" placeholder="john.doe@gmail.com" autocomplete />
                        </div>
                        <div class="mb-5">
                            <label for="message" class="block mb-2 text-sm font-medium text-gray-900">Your message</label>
                            <textarea id="message" v-model="message" rows="4" class="bg-white border border-gray-300 text-gray-900 text-sm rounded-lg block w-full p-2.5 " placeholder="Leave a comment..."></textarea>
                        </div>
                        <button type="submit" @click="sendEmail" aria-label="Submit form contact" title="Submit" :disabled="isLoading" class="text-white bg-gray-900 hover:bg-gray-800 font-semibold rounded-lg text-sm w-full px-5 py-2.5 text-center hover:scale-110 duration-500">
                            Submit
                        </button>
                    </form>
                </div>
            </div>
            <div v-if="isLoading" role="status" class="absolute -translate-x-1/2 -translate-y-1/2 top-2/4 left-1/2 flex flex-col items-center">
                <svg aria-hidden="true" class="w-8 h-8 text-white animate-spin fill-gray-900" viewBox="0 0 100 101" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M100 50.5908C100 78.2051 77.6142 100.591 50 100.591C22.3858 100.591 0 78.2051 0 50.5908C0 22.9766 22.3858 0.59082 50 0.59082C77.6142 0.59082 100 22.9766 100 50.5908ZM9.08144 50.5908C9.08144 73.1895 27.4013 91.5094 50 91.5094C72.5987 91.5094 90.9186 73.1895 90.9186 50.5908C90.9186 27.9921 72.5987 9.67226 50 9.67226C27.4013 9.67226 9.08144 27.9921 9.08144 50.5908Z" fill="currentColor"/>
                    <path d="M93.9676 39.0409C96.393 38.4038 97.8624 35.9116 97.0079 33.5539C95.2932 28.8227 92.871 24.3692 89.8167 20.348C85.8452 15.1192 80.8826 10.7238 75.2124 7.41289C69.5422 4.10194 63.2754 1.94025 56.7698 1.05124C51.7666 0.367541 46.6976 0.446843 41.7345 1.27873C39.2613 1.69328 37.813 4.19778 38.4501 6.62326C39.0873 9.04874 41.5694 10.4717 44.0505 10.1071C47.8511 9.54855 51.7191 9.52689 55.5402 10.0491C60.8642 10.7766 65.9928 12.5457 70.6331 15.2552C75.2735 17.9648 79.3347 21.5619 82.5849 25.841C84.9175 28.9121 86.7997 32.2913 88.1811 35.8758C89.083 38.2158 91.5421 39.6781 93.9676 39.0409Z" fill="currentFill"/></svg>
                <span class="sr-only">Loading...</span>
            </div>
        </div>

    </section>
</template>

<style scoped>
@keyframes slideInFromLeft {
    0% {
        transform: translateX(-10%);
        opacity: 0;
    }
    100% {
        transform: translateX(0);
        opacity: 1;
    }
}

.animate-slide-in-left {
    animation: slideInFromLeft 0.5s ease-out;
}
</style>