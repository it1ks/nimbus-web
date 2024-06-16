<script setup>
import AuthenticatedLayout from "@/Layouts/AuthenticatedLayout.vue";
import { Head } from "@inertiajs/vue3";
</script>

<template>
    <Head title="Dashboard" />

    <AuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                Dashboard
            </h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="lg:flex gap-4 items-stretch">
                    <div
                        class="bg-white md:p-2 p-6 rounded-lg border border-gray-200 mb-4 lg:mb-0 shadow-md lg:w-[35%]"
                    >
                        <div
                            class="flex justify-center items-center space-x-5 h-full"
                        >
                            <div>
                                <p>Saldo Awal</p>

                                <p>Rp. 100.000</p>
                            </div>
                            <img
                                src="https://www.emprenderconactitud.com/img/Wallet.png"
                                alt="wallet"
                                class="h-10 md:h-10 w-30"
                            />
                        </div>
                    </div>

                    <div
                        class="bg-white p-4 rounded-lg xs:mb-4 max-w-full shadow-md lg:w-[65%]"
                    >
                        <div class="flex flex-wrap justify-between h-full">
                            <a
                                class="flex-1 bg-gradient-to-r bg-indigo-800 rounded-lg flex flex-col items-center justify-center p-4 space-y-2 border border-gray-200 m-2"
                            >
                                <i
                                    class="fas fa-hand-holding-usd text-white text-4xl"
                                ></i>
                                <p class="text-white">Deposit</p>
                            </a>
                        </div>
                    </div>
                </div>

                <!-- Tabla -->
                <div class="bg-white rounded-lg p-4 shadow-md my-4">
                    <table class="table-auto w-full">
                        <thead>
                            <tr>
                                <th
                                    class="px-4 py-2 text-left border-b-2 w-full"
                                >
                                    <h2 class="text-ml font-bold text-gray-600">
                                        Transaksi
                                    </h2>
                                </th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr class="border-b w-full">
                                <td class="px-4 py-2 text-left align-top w-1/2">
                                    <div>
                                        <h2>Deposit</h2>
                                        <p>24/07/2024</p>
                                    </div>
                                </td>
                                <td
                                    class="px-4 py-2 text-right text-cyan-500 w-1/2"
                                >
                                    <p><span>Rp.100.000</span></p>
                                </td>
                            </tr>
                            <tr class="border-b w-full">
                                <td class="px-4 py-2 text-left align-top w-1/2">
                                    <div>
                                        <h2>Deposit</h2>
                                        <p>24/06/2024</p>
                                    </div>
                                </td>
                                <td
                                    class="px-4 py-2 text-right text-cyan-500 w-1/2"
                                >
                                    <p><span>Rp.150.000</span></p>
                                </td>
                            </tr>
                            <tr class="border-b w-full">
                                <td class="px-4 py-2 text-left align-top w-1/2">
                                    <div>
                                        <h2>Deposit</h2>
                                        <p>02/05/2024</p>
                                    </div>
                                </td>
                                <td
                                    class="px-4 py-2 text-right text-cyan-500 w-1/2"
                                >
                                    <p><span>Rp.500.000</span></p>
                                </td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template>
