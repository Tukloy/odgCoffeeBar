<script setup>
import { RouterView } from 'vue-router'
import Navbar from '@/components/Navbar.vue';
import MiniNavbar from '@/components/MiniNavbar.vue';
import { reactive, watch } from 'vue';

const state = reactive({
  isMenuOpen: false
});

const handleToggleMenu = (isMenuOpen) => {
  state.isMenuOpen = isMenuOpen;
};

watch(() => state.isMenuOpen, (newValue) => {
  state.isMenuOpen = newValue;
});

</script>

<template>
  <div>
    <header>
      <Navbar :isOpen="state.isMenuOpen" @toggle-menu="handleToggleMenu" />
      <MiniNavbar :isOpen="state.isMenuOpen" @toggle-menu="handleToggleMenu" />
    </header>

    <main class="py-22 sm:py-22 md:py-22 lg:py-24 xl:py-24 2xl:py-24">
      <RouterView />
    </main>
  </div>
</template>

<style scoped></style>
