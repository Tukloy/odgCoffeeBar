<script setup>
import { RouterLink } from 'vue-router'
import { reactive } from 'vue';

const props = defineProps({
    isOpen: Boolean,
});

const emit = defineEmits(['toggle-menu']);

const toggleMenu = () => {
    emit('toggle-menu', !props.isOpen);
};
</script>
<template>
    <nav
        class="flex items-center bg-white justify-between py-4 sm:py-4 lg:py-6 px-6 sm:px-10 lg:px-20 border-b border-gray-300 shadow-lg fixed right-0 left-0  z-30">
        <div class="flex gap-x-4 text-sm uppercase font-bold items-center">
            <RouterLink to="/" class="">
                <img src="/logo/logo.png" class="h-10 w-10  sm:h-10 sm:w-10 lg:h-12 lg:w-12" alt="logo">
            </RouterLink>
            <div class="hidden gap-x-4 sm:flex">
                <RouterLink to="/menu" class="hover:text-green-800 ease-in-out duration-300">Menu</RouterLink>
                <RouterLink to="/merchandise" class="hover:text-green-800 ease-in-out duration-300">Merchandise
                </RouterLink>
                <RouterLink to="/about" class="hover:text-green-800 ease-in-out duration-300">About us</RouterLink>
            </div>
        </div>
        <div class="block md:hidden hover:bg-green-800 ease-in-out duration-300 rounded-full p-2 cursor-pointer">
            <button @click="toggleMenu" class="text-2xl focus:bg-gray-100 px-2 py-1 rounded-full">
                <i :class="props.isOpen ? 'pi pi-times' : 'pi pi-bars'"></i>
            </button>
        </div>
        <div class="flex gap-x-4 items-center hidden lg:flex-row font-bold md:flex-col sm:flex">
            <div class="hover:text-green-800 ease-in-out duration-300 cursor-pointer flex gap-x-1 items-center">
                <i class="pi pi-map-marker"></i>
                <label>Find a Store</label>
            </div>
            <div class="flex gap-x-2">
                <button class="border border-1 py-1 px-4 rounded-full hover:bg-gray-200/75 cursor-pointer">Cart</button>
                <button
                    class="border border-1 py-1 px-4 rounded-full bg-black text-white hover:bg-black/75 cursor-pointer">Chat
                    us</button>
            </div>
        </div>
    </nav>
    <nav class="block md:hidden">

    </nav>
</template>