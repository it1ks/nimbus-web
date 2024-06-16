<script setup>
import ApplicationLogo from "@/Components/ApplicationLogo.vue";
import { Link } from "@inertiajs/vue3";
</script>

<template>
    <div
        class="min-h-screen flex flex-col sm:justify-center items-center pt-6 sm:pt-0"
        style="
            background-image: url('img/background-1.png');
            background-size: cover;
            background-position: center;
        "
    >
        <div>
            <Link href="/">
                <ApplicationLogo
                    class="w-32 h-32 inline-block mb-6 text-3xl font-bold tracking-wider uppercase"
                />
            </Link>
        </div>

        <div class="w-screen max-w-sm px-4 py-6 space-y-6 bg-white rounded-xl">
            <slot />
        </div>
    </div>
</template>
