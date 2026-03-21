<script setup>
import { RouterLink } from 'vue-router'
</script>
<template>
    <nav class="flex items-center justify-between py-4 px-14 border-b border-gray-300">
        <div class="flex gap-x-4 text-sm uppercase font-bold items-center">
            <RouterLink to="/" class="">
                 <img src="/logo/logo.png" class="h-12 w-12" alt="logo">
            </RouterLink>
            <RouterLink to="/menu" class="hover:text-green-800 ease-in-out duration-300">Menu</RouterLink>
            <RouterLink to="/merchandise" class="hover:text-green-800 ease-in-out duration-300">Merchandise</RouterLink>
            <RouterLink to="/about" class="hover:text-green-800 ease-in-out duration-300">About us</RouterLink>
        </div>
        <div class="flex gap-x-4 items-center font-bold">
            <div class="hover:text-green-800 ease-in-out duration-300 cursor-pointer flex gap-x-1 items-center">
                <i class="pi pi-map-marker"></i>
                <label>find store</label>
            </div>
            <div class="flex gap-x-2">
                <button class="border border-1 py-1 px-4 rounded-full hover:bg-gray-200/75 cursor-pointer">Cart</button>
                <button class="border border-1 py-1 px-4 rounded-full bg-black text-white hover:bg-black/75 cursor-pointer">Chat us</button>
            </div>
        </div>
    </nav>
</template>