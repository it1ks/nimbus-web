<script setup>
import { Head, Link } from "@inertiajs/vue3";
import FrontendLayout from "@/Layouts/FrontendLayout.vue";
import Hero from "@/Components/Frontend/Hero.vue";
import Content from "@/Components/Frontend/Content.vue";
import Promo from "@/Components/Frontend/Promo.vue";
import Team from "@/Components/Frontend/Team.vue";
import Pricing from "@/Components/Frontend/Pricing.vue";
import Testimonials from "@/Components/Frontend/Testimonials.vue";
import Footer from "@/Components/Frontend/Footer.vue";
</script>

<template>
    <Head title="Cloud Hosting & Web Hosting" />
    <FrontendLayout>
        <Hero />
        <Content />
        <Promo />
        <Team />
        <Pricing />
        <Testimonials />
        <Footer />
    </FrontendLayout>
</template>
