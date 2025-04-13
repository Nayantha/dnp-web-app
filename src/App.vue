<script lang="ts" setup>
import Header from './components/Header.vue'
import Footer from "./components/Footer.vue";
import Main from "./components/Main.vue";
</script>

<template>
    <div class="md:w-11/12 mx-auto min-h-screen flex flex-col dark:bg-black bg-white">
        <Header/>
        <Main/>
        <Footer/>
    </div>
</template>

<style scoped>
</style>
