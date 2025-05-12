<script setup>
import { Head, Link } from '@inertiajs/vue3';
import MegaMenu from '@/components/home/MegaMenu.vue';
</script>

<template>

    <Head title="Upwork | The job Market Place">
        <link rel="preconnect" href="https://rsms.me/" />
        <link rel="stylesheet" href="https://rsms.me/inter/inter.css" />
    </Head>
    <div class="mx-auto max-w-[1540px]">
        <header class="p-2 pt-4">
            <nav class="flex items-center justify-between gap-4">
                <!-- upwork logo -->
                <Link :href="route('home')">
                <img src="/images/logoo.png" class="h-6" alt="">
                </Link>

                <MegaMenu />
                <!-- auth buttons -->
                <div class="flex items-center">
                    <Link v-if="$page.props.auth.user" :href="route('dashboard')"
                        class="inline-block rounded-sm border border-[#19140035] px-5 py-1.5 text-sm leading-normal text-[#1b1b18] hover:border-[#1915014a] dark:border-[#3E3E3A] dark:text-[#EDEDEC] dark:hover:border-[#62605b]">
                    Dashboard
                    </Link>
                    <template v-else>
                        <Link :href="route('login')"
                            class="inline-block rounded-sm border border-transparent px-5 py-1.5 text-sm leading-normal text-[#1b1b18] hover:border-[#19140035] dark:text-[#EDEDEC] dark:hover:border-[#3E3E3A]">
                        Log in
                        </Link>
                        <Link :href="route('register')"
                            class="bg-[#0E8B00] text-white text-sm px-4 rounded-full p-2">
                        Sign Up
                        </Link>
                    </template>
                </div>
            </nav>
        </header>
    </div>
</template>
