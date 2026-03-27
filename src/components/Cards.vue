<script setup>
import { reactive } from 'vue';

const cards = reactive([
    {
        title: 'A Cozy Coffee Moment',
        description: 'Warm sips and creamy swirls to slow down your day and savor the little things. ☕',
        image: '/images/card1.jpg',
    },
    {
        title: 'Sweet Little Indulgences',
        description: 'Delicate, creamy bites bursting with flavor — perfect for a moment of pure delight. 🍰',
        image: '/images/card2.jpg',
    },
    {
        title: 'Card 3',
        description: 'This is the description for card 3.',
        image: '/images/card3.jpg',
    },
]);
</script>
<template>
    <section>
        <div class="container mx-auto py-8 grid grid-cols-2 gap-8">
            <div v-for="card in cards" :key="card.title">
                <img class="h-[400px] w-full" :src="card.image" :alt="card.title">
                <div class="py-[40px] px-[74px] flex flex-col items-center justify-center gap-y-6">
                    <h1 class="text-2xl font-bold">{{ card.title }}</h1>
                    <p class="font-medium mb-2">{{ card.description }}</p>
                    <button
                        class="border border-1 border-black font-bold py-1 px-4 rounded-full hover:bg-gray-200/75 cursor-pointer">Discover
                        More</button>
                </div>
            </div>
        </div>
    </section>
</template>