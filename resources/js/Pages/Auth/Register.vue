<script setup>
import Checkbox from "@/Components/Checkbox.vue";
import GuestLayout from "@/Layouts/GuestLayout.vue";
import InputError from "@/Components/InputError.vue";
import InputLabel from "@/Components/InputLabel.vue";
import PrimaryButton from "@/Components/PrimaryButton.vue";
import TextInput from "@/Components/TextInput.vue";
import { Head, Link, useForm } from "@inertiajs/vue3";

const form = useForm({
    name: "",
    email: "",
    password: "",
    password_confirmation: "",
});

const submit = () => {
    form.post(route("register"), {
        onFinish: () => form.reset("password", "password_confirmation"),
    });
};
</script>

<template>
    <GuestLayout>
        <Head title="Register" />

        <form @submit.prevent="submit">
            <h1 class="text-2xl font-sans font-semibold text-gray-700">
                Register
            </h1>
            <hr class="mt-2 py-2 border-b-1 border-gray-300" />
            <div>
                <TextInput
                    id="name"
                    type="text"
                    class="mt-1 block w-full placeholder-gray-400"
                    v-model="form.name"
                    required
                    autofocus
                    autocomplete="name"
                    placeholder="Fullname"
                />

                <InputError class="mt-2" :message="form.errors.name" />
            </div>

            <div class="mt-4">
                <TextInput
                    id="email"
                    type="email"
                    class="mt-1 block w-full placeholder-gray-400"
                    v-model="form.email"
                    required
                    autocomplete="username"
                    placeholder="Email"
                />

                <InputError class="mt-2" :message="form.errors.email" />
            </div>

            <div class="mt-4">
                <TextInput
                    id="password"
                    type="password"
                    class="mt-1 block w-full placeholder-gray-400"
                    v-model="form.password"
                    required
                    autocomplete="new-password"
                    placeholder="New password"
                />

                <InputError class="mt-2" :message="form.errors.password" />
            </div>

            <div class="mt-4">
                <TextInput
                    id="password_confirmation"
                    type="password"
                    class="mt-1 block w-full placeholder-gray-400"
                    v-model="form.password_confirmation"
                    required
                    autocomplete="new-password"
                    placeholder="Confirm new password"
                />

                <InputError
                    class="mt-2"
                    :message="form.errors.password_confirmation"
                />
            </div>

            <div class="block mt-5">
                <label class="flex items-center">
                    <Checkbox />
                    <p class="ms-1 text-sm text-gray-500">
                        I have read and agree to the
                        <span class="text-cyan-600">Terms of Service</span>
                    </p>
                </label>
            </div>

            <div class="text-center mt-6">
                <PrimaryButton
                    class="justify-center bg-indigo-600 text-white font-bold py-2 px-4 w-full rounded hover:bg-indigo-800"
                    :class="{ 'opacity-25': form.processing }"
                    :disabled="form.processing"
                >
                    Register
                </PrimaryButton>
            </div>
            <div class="mt-7 flex items-center justify-between">
                <span class="border-b w-full lg:w-full"></span>
                <a class="text-sm text-center text-gray-600 uppercase">or </a>
                <span class="border-b w-full lg:w-full"></span>
            </div>

            <div class="text-center justify-center mt-6">
                <button
                    class="w-full bg-white active:bg-blueGray-50 text-blueGray-700 font-sans px-4 py-2 rounded outline-none border border-gray-300 focus:outline-none uppercase inline-flex items-center justify-center font-semibold text-xs"
                    type="button"
                >
                    <img
                        alt="..."
                        class="w-5 mr-2"
                        src="https://demos.creative-tim.com/notus-js/assets/img/google.svg"
                    />Sign up with Google
                </button>
            </div>

            <div class="mt-7 flex items-center justify-between">
                <span class="border-b w-full lg:w-full"></span>

                <span class="border-b w-full lg:w-full"></span>
            </div>

            <div class="flex mt-4">
                <Link
                    :href="route('login')"
                    class="text-sm text-cyan-600 hover:text-cyan-900 rounded-md"
                >
                    Already registered?
                </Link>
            </div>
        </form>
    </GuestLayout>
</template>
