<script setup>
import AuthenticatedLayout from "@/Layouts/AuthenticatedLayout.vue";
import { Head } from "@inertiajs/vue3";
import Product from "@/Pages/Store/Product.vue";
import { ref, computed } from "vue";

const products = ref([
    {
        id: 1,
        name: "Virtual Machine XXS",
        category: "Virtual Machine",
        cpu: "1",
        ram: "1 GB",
        storage: "20 GB",
        price: 90.099,
    },
    {
        id: 2,
        name: "Virtual Machine XS",
        category: "Virtual Machine",
        cpu: "2",
        ram: "4 GB",
        storage: "40 GB",
        price: 180.099,
    },
    {
        id: 3,
        name: "Virtual Machine S",
        category: "Virtual Machine",
        cpu: "4",
        ram: "4 GB",
        storage: "70 GB",
        price: 360.099,
    },
    {
        id: 4,
        name: "Virtual Machine M",
        category: "Virtual Machine",
        cpu: "8",
        ram: "8 GB",
        storage: "120 GB",
        price: 720.099,
    },
    {
        id: 5,
        name: "Basic Hosting",
        category: "Hosting",
        cpu: "2",
        ram: "2 GB",
        storage: "50 GB",
        price: 100.0,
    },
    {
        id: 6,
        name: "Premium Hosting",
        category: "Hosting",
        cpu: "4",
        ram: "8 GB",
        storage: "200 GB",
        price: 500.0,
    },
    {
        id: 7,
        name: "Storage Plan A",
        category: "Storage",
        cpu: "1",
        ram: "1 GB",
        storage: "100 GB",
        price: 50.0,
    },
    {
        id: 8,
        name: "Storage Plan B",
        category: "Storage",
        cpu: "2",
        ram: "2 GB",
        storage: "500 GB",
        price: 200.0,
    },
    {
        id: 9,
        name: "Protect Basic",
        category: "Protect",
        cpu: "1",
        ram: "1 GB",
        storage: "10 GB",
        price: 70.0,
    },
    {
        id: 10,
        name: "Protect Advanced",
        category: "Protect",
        cpu: "2",
        ram: "2 GB",
        storage: "20 GB",
        price: 150.0,
    },
    {
        id: 11,
        name: "SSL Certificate Basic",
        category: "SSL Certificate",
        cpu: "N/A",
        ram: "N/A",
        storage: "N/A",
        price: 30.0,
    },
    {
        id: 12,
        name: "SSL Certificate Advanced",
        category: "SSL Certificate",
        cpu: "N/A",
        ram: "N/A",
        storage: "N/A",
        price: 100.0,
    },
]);

const selectedCategory = ref("All");

const filteredProducts = computed(() => {
    if (selectedCategory.value === "All") {
        return products.value;
    }
    return products.value.filter(
        (product) => product.category === selectedCategory.value
    );
});

const setCategory = (category) => {
    selectedCategory.value = category;
};
</script>

<template>
    <Head title="Store" />
    <AuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                Store
            </h2>
        </template>
        <div class="container mt-2 mx-auto">
            <h1 class="text-bold text-md py-4">Choose Package</h1>
            <div
                class="mb-4 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-5 gap-3"
            >
                <button
                    class="middle none center rounded-lg bg-indigo-600 py-3 px-6 font-sans text-xs font-bold uppercase text-white shadow-md transition-all hover:shadow-lg focus:opacity-[0.85]"
                    @click="setCategory('Virtual Machine')"
                >
                    Virtual Machine
                </button>
                <button
                    class="middle none center rounded-lg bg-indigo-600 py-3 px-6 font-sans text-xs font-bold uppercase text-white shadow-md transition-all hover:shadow-lg focus:opacity-[0.85]"
                    @click="setCategory('Hosting')"
                >
                    Hosting
                </button>
                <button
                    class="middle none center rounded-lg bg-indigo-600 py-3 px-6 font-sans text-xs font-bold uppercase text-white shadow-md transition-all hover:shadow-lg focus:opacity-[0.85]"
                    @click="setCategory('Storage')"
                >
                    Storage
                </button>
                <button
                    class="middle none center rounded-lg bg-indigo-600 py-3 px-6 font-sans text-xs font-bold uppercase text-white shadow-md transition-all hover:shadow-lg focus:opacity-[0.85]"
                    @click="setCategory('Protect')"
                >
                    Protect
                </button>
                <button
                    class="middle none center rounded-lg bg-indigo-600 py-3 px-6 font-sans text-xs font-bold uppercase text-white shadow-md transition-all hover:shadow-lg focus:opacity-[0.85]"
                    @click="setCategory('SSL Certificate')"
                >
                    SSL Certificate
                </button>
            </div>

            <h1 class="text-bold text-md py-4">
                {{
                    selectedCategory === "All"
                        ? "All Products"
                        : selectedCategory
                }}
            </h1>
            <div
                class="flex text-center grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-3"
            >
                <Product
                    v-for="product in filteredProducts"
                    :key="product.id"
                    :product="product"
                />
            </div>
        </div>
    </AuthenticatedLayout>
</template>

<style scoped>
.container {
    padding: 0 1rem;
}
</style>
