<script setup>
import { reactive } from 'vue';

const props = defineProps({
    isOpen: {
        type: Boolean,
        required: true
    }
});

const emit = defineEmits(['toggle-menu']);
</script>
<template>
    <nav
        :class="`bg-black/20 h-screen w-full fixed right-0 top-[88px] z-20 transition-opacity duration-200 ${props.isOpen ? 'opacity-100 pointer-events-auto' : 'opacity-0 pointer-events-none'}`">
        <div
            :class="`shadow-lg bg-white h-screen w-[70%] fixed right-0 ease-in-out duration-300 transform ${props.isOpen ? 'translate-x-0' : 'translate-x-full'} z-20`">
            <div class="flex flex-col gap-y-6 text-gray-800 font-bold px-8 mt-10">
                <RouterLink to="/menu" @click="emit('toggle-menu', false)"
                    class="hover:text-green-800 ease-in-out duration-300 uppercase">Menu</RouterLink>
                <RouterLink to="/merchandise" @click="emit('toggle-menu', false)"
                    class="hover:text-green-800 ease-in-out duration-300 uppercase">
                    Merchandise
                </RouterLink>
                <RouterLink to="/about" @click="emit('toggle-menu', false)"
                    class="hover:text-green-800 ease-in-out duration-300 uppercase">About us
                </RouterLink>
                <hr class="border border-b border-gray-300">
                <div class="hover:text-green-800 ease-in-out duration-300 cursor-pointer flex gap-x-1 items-center">
                    <i class="pi pi-map-marker"></i>
                    <label class="text-gray-600">Find a Store</label>
                </div>
                <div class="flex flex-col gap-y-4 items-start">
                    <button
                        class="inline-block border py-1 px-4 rounded-full hover:bg-gray-200/75 cursor-pointer">Cart</button>
                    <button
                        class="inline-block border py-1 px-4 rounded-full bg-black text-white hover:bg-black/75 cursor-pointer">Chat
                        us</button>
                </div>
            </div>
        </div>
    </nav>
</template>