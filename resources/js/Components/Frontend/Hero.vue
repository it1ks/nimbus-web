<script setup></script>
<template>
    <section id="hero">
        <header
            class="min-h-screen"
            style="
                background-image: url('img/background-2.png');
                background-size: cover;
                background-position: center;
            "
        >
            <nav>
                <div class="container flex flex-col items-center p-6 mx-auto">
                    <div
                        class="flex items-center py-2 justify-center mt-6 text-white capitalize"
                    >
                        <a href="/" class="text-gray-300 mx-1.5 sm:mx-6"
                            >home</a
                        >

                        <a
                            href="#services"
                            class="text-white hover:text-gray-300 mx-1.5 sm:mx-6"
                            >services</a
                        >

                        <a
                            href="#teams"
                            class="text-white hover:text-gray-300 mx-1.5 sm:mx-6"
                            >teams</a
                        >

                        <a
                            href="#pricing"
                            class="text-white hover:text-gray-300 mx-1.5 sm:mx-6"
                            >pricing</a
                        >

                        <a
                            href="#testimonials"
                            class="text-white hover:text-gray-300 mx-1.5 sm:mx-6"
                            >testimonials</a
                        >

                        <a
                            :href="route('login')"
                            class="text-white hover:text-gray-300 border-solid border px-2 rounded sm:mx-5"
                            >login</a
                        >
                    </div>
                </div>
            </nav>

            <div
                class="py-8 px-4 mx-auto max-w-screen-xl text-center lg:py-20 lg:px-12"
            >
                <a
                    class="inline-flex justify-between items-center py-3 px-1 text-sm text-white"
                >
                    <span class="text-base font-medium"
                        >Welcome to NimbusWeb</span
                    >
                </a>
                <h1
                    class="mb-4 text-4xl font-extrabold tracking-tight leading-none text-white md:text-5xl lg:text-6xl"
                >
                    Beyond the Cloud: <br />Your Total Cloud Solutions Partner
                </h1>
                <p
                    class="mb-8 text-base font-normal text-white lg:text-base sm:px-16 xl:px-48"
                >
                    Startup Framework gives you complete freedom over your
                    creative process — you don’t have to think about any
                    technical aspects. There are no limits and absolutely no
                    coding.
                </p>
                <a
                    :href="route('login')"
                    class="uppercase shadow bg-indigo-800 hover:bg-indigo-700 focus:shadow-outline focus:outline-none text-white text-sm font-semibold py-3 px-10 rounded"
                >
                    Lihat Layanan
                </a>
            </div>
        </header>
    </section>
</template>
