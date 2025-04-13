<script lang="ts" setup>
import Header from './components/Header.vue'
import Footer from "./components/Footer.vue";
</script>

<template>
    <div class="w-11/12 mx-auto min-h-screen flex flex-col dark:bg-black bg-white">
        <Header/>
        <main class="flex-grow">
            <slot />
        </main>
        <Footer/>
    </div>
</template>

<style scoped>
</style>
