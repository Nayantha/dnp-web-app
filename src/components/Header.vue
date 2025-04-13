<template>
    <div class="sm:px-8 w-full p-5">
        <div class="mx-auto w-full max-w-7xl lg:px-8">
            <div class="relative px-4 sm:px-8 lg:px-12">
                <div class="mx-auto max-w-2xl lg:max-w-5xl">
                    <div class="relative flex gap-4">
                        <div class="flex flex-1"/>

                        <!-- Centered Navigation -->
                        <div class="flex flex-1 justify-end md:justify-center">
                            <!-- Mobile Menu Button + menu popover -->
                            <Popover class="pointer-events-auto md:hidden">
                                <PopoverButton
                                        class="group flex items-center rounded-full bg-white/90 px-4 py-2 text-sm font-medium text-zinc-800 shadow-lg ring-1 ring-zinc-900/5 shadow-zinc-800/5 backdrop-blur-sm dark:bg-zinc-800/90 dark:text-zinc-200 dark:ring-white/10 dark:hover:ring-white/20">
                                    Menu
                                    <ChevronDownIcon aria-hidden="true" class="size-5 flex-none"/>
                                </PopoverButton>
                                <transition enter-active-class="transition ease-out duration-200"
                                            enter-from-class="opacity-0 translate-y-1"
                                            enter-to-class="opacity-100 translate-y-0"
                                            leave-active-class="transition ease-in duration-150"
                                            leave-from-class="opacity-100 translate-y-0"
                                            leave-to-class="opacity-0 translate-y-1">
                                    <PopoverPanel
                                            class="absolute top-full -left-8 z-10 mt-3 w-screen max-w-md overflow-hidden rounded-3xl bg-white dark:bg-black shadow-lg ring-1 ring-gray-900/5">
                                        <div class="p-4">
                                            <div v-for="item in navMenu" :key="item.name"
                                                 class="group relative flex items-center gap-x-6 rounded-lg p-4 text-sm/6 hover:text-gray-500">
                                                <div class="flex-auto">
                                                    <a :href="item.href"
                                                       class="block font-semibold block px-3 py-2 transition hover:text-teal-500 dark:hover:text-teal-400">
                                                        {{ item.name }}
                                                    </a>
                                                </div>
                                            </div>
                                        </div>
                                    </PopoverPanel>
                                </transition>
                            </Popover>

                            <!-- Desktop Navigation -->
                            <nav class="pointer-events-auto hidden md:block">
                                <ul class="flex rounded-full bg-white/90 px-3 text-sm font-medium text-zinc-800 shadow-lg ring-1 ring-zinc-900/5 shadow-zinc-800/5 backdrop-blur-sm dark:bg-zinc-800/90 dark:text-zinc-200 dark:ring-white/10">
                                    <li v-for="item in navMenu" :key="item.name">
                                        <a :href="item.href"
                                           class="block px-3 py-2 transition hover:text-teal-500 dark:hover:text-teal-400">
                                            {{ item.name }}
                                        </a>
                                    </li>
                                </ul>
                            </nav>
                        </div>

                        <!-- Theme Toggle -->
                        <div class="flex justify-end md:flex-1">
                            <div class="pointer-events-auto">
                                <button
                                        aria-label="Switch to light theme"
                                        class="group rounded-full bg-white/90 px-3 py-2 shadow-lg ring-1 ring-zinc-900/5 shadow-zinc-800/5 backdrop-blur-sm transition dark:bg-zinc-800/90 dark:ring-white/10 dark:hover:ring-white/20"
                                        @click="toggleDark()"
                                >
                                    <!-- Light Mode Icon -->
                                    <svg
                                            class="h-6 w-6 fill-zinc-100 stroke-teal-500 transition group-hover:fill-zinc-200 group-hover:stroke-zinc-700 dark:hidden"
                                            stroke-linecap="round"
                                            stroke-linejoin="round"
                                            stroke-width="1.5"
                                            viewBox="0 0 24 24"
                                    >
                                        <path d="M8 12.25A4.25 4.25 0 0 1 12.25 8a4.25 4.25 0 0 1 4.25 4.25 4.25 4.25 0 0 1-4.25 4.25A4.25 4.25 0 0 1 8 12.25Z"/>
                                        <path
                                                d="M12.25 3v1.5M21.5 12.25H20M18.791 18.791l-1.06-1.06M18.791 5.709l-1.06 1.06M12.25 20v1.5M4.5 12.25H3M6.77 6.77 5.709 5.709M6.77 17.73l-1.061 1.061"
                                                fill="none"
                                        />
                                    </svg>
                                    <!-- Dark Mode Icon -->
                                    <svg
                                            class="hidden h-6 w-6 fill-zinc-700 stroke-zinc-500 transition dark:block"
                                            viewBox="0 0 24 24"
                                    >
                                        <path
                                                d="M17.25 16.22a6.937 6.937 0 0 1-9.47-9.47 7.451 7.451 0 1 0 9.47 9.47ZM12.75 7C17 7 17 2.75 17 2.75S17 7 21.25 7C17 7 17 11.25 17 11.25S17 7 12.75 7Z"
                                                stroke-linecap="round"
                                                stroke-linejoin="round"
                                                stroke-width="1.5"
                                        />
                                    </svg>
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script lang="ts" setup>
import { useDark, useToggle } from '@vueuse/core'
import { Popover, PopoverButton, PopoverPanel, } from '@headlessui/vue'
import { ChevronDownIcon } from '@heroicons/vue/20/solid'

const isDark = useDark();
const toggleDark = useToggle(isDark);

const navMenu = [
    { name: 'Shoots', description: 'View recent shoots.', href: '/shoots' },
    { name: 'Testimonials', description: 'Get a to know about us.', href: '/testimonials' },
    { name: 'About', description: 'Get a to know about us.', href: '/about' },
    { name: 'Contact', description: 'Get a to know about us.', href: '/links' },
];
</script>