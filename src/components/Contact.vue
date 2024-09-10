<script setup>
import { ref } from 'vue'

const name = ref('');
const email = ref('');
const message = ref('');

const sendEmail = () => {
    window.open('mailto:test@example.com?subject=subject&body=body');
}
</script>

<template>
    <section id="contact">

        <div class="mx-auto max-w-2xl py-32 sm:py-48 lg:py-48 px-8 md:px-0">
            <div class="flex flex-col justify-center items-center slide-animation">
                <h2 class="mb-14 text-4xl font-bold tracking-tight text-gray-900 sm:text-6xl">Contact me</h2>
                <div class="rounded-lg p-8 flex flex-col items-center w-full bg-[#F6F6F6] shadow-lg">
                    <form action="#" method="post" class="min-w-full">
                        <div class="mb-5">
                            <label for="name" class="block mb-2 text-sm font-medium text-gray-900">Your name</label>
                            <input type="text" id="name" class="bg-white border border-gray-300 text-gray-900 text-sm rounded-lg block w-full p-2.5" placeholder="John Doe" />
                        </div>
                        <div class="mb-5">
                            <label for="email" class="block mb-2 text-sm font-medium text-gray-900">Your email</label>
                            <input type="email" id="email" class="bg-white border border-gray-300 text-gray-900 text-sm rounded-lg block w-full p-2.5" placeholder="john.doe@gmail.com" />
                        </div>
                        <div class="mb-5">
                            <label for="message" class="block mb-2 text-sm font-medium text-gray-900">Your message</label>
                            <textarea id="message" rows="4" class="bg-white border border-gray-300 text-gray-900 text-sm rounded-lg block w-full p-2.5 " placeholder="Leave a comment..."></textarea>
                        </div>
                        <button type="submit" @click="sendEmail" aria-label="Submit form contact" title="Submit" class="text-white bg-gray-900 hover:bg-gray-800 font-semibold rounded-lg text-sm w-full px-5 py-2.5 text-center hover:scale-110 duration-500">
                            Submit
                        </button>
                    </form>
                </div>
            </div>
        </div>

    </section>
</template>