<template>
    <div class="bg-white border-sm p-4 rounded-lg shadow-sm">
        <h3 class="font-semibold text-md">{{ product.name }}</h3>
        <hr class="mt-2 py-2 border-b-1 border-gray-300" />
        <p class="text-gray-600 mt-2">vCPU</p>
        <p class="text-blue-700 font-semibold">{{ product.cpu }}</p>
        <p class="text-gray-600 mt-2">RAM</p>
        <p class="text-blue-700 font-semibold">{{ product.ram }}</p>
        <p class="text-gray-600 mt-2">Storage</p>
        <p class="text-blue-700 font-semibold">{{ product.storage }}</p>
        <p class="text-gray-600 mt-2">Monthly</p>
        <p class="text-blue-700 mb-4 font-semibold">Rp. {{ product.price }}</p>
        <PrimaryButton
            class="ml-2 justify-center bg-indigo-600 text-white font-bold py-1 px-6 w-full rounded hover:bg-indigo-800"
        >
            Order Now
        </PrimaryButton>
    </div>
</template>

<script setup>
import { defineProps } from "vue";

const props = defineProps({
    product: {
        type: Object,
        required: true,
    },
});
</script>
