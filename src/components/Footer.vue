<template>
    <div class="mx-auto w-full max-w-7xl lg:px-8">
        <div class="border-t border-zinc-100 pt-10 pb-16 dark:border-zinc-700/40">
            <div class="relative px-4 sm:px-8 lg:px-12">
                <div class="mx-auto max-w-2xl lg:max-w-5xl">
                    <div class="flex flex-col items-center justify-between gap-6 md:flex-row">
                        <div class="flex flex-wrap justify-center gap-x-6 gap-y-1 text-sm font-medium text-zinc-800 dark:text-zinc-200">
                            <a v-for="item in footerMenu" :key="item.name" :href="item.href"
                               class="transition hover:text-teal-500 dark:hover:text-teal-400">
                                {{ item.name }}
                            </a>
                        </div>
                        <p class="text-sm text-zinc-400 dark:text-zinc-500">
                            © <!-- -->2025<!-- --> Nayantha Koralegama.All rights reserved.
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script lang="ts" setup>
const footerMenu = [
    { name: 'Shoots', description: 'View recent shoots.', href: '/shoots' },
    { name: 'Testimonials', description: 'Get a to know about us.', href: '/testimonials' },
    { name: 'About', description: 'Get a to know about us.', href: '/about' },
    { name: 'Contact', description: 'Get a to know about us.', href: '/links' },
];
</script>

<style scoped>

</style>