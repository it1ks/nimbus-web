<script setup>
import Checkbox from "@/Components/Checkbox.vue";
import GuestLayout from "@/Layouts/GuestLayout.vue";
import InputError from "@/Components/InputError.vue";
import PrimaryButton from "@/Components/PrimaryButton.vue";
import TextInput from "@/Components/TextInput.vue";
import { Head, Link, useForm } from "@inertiajs/vue3";

defineProps({
    canResetPassword: {
        type: Boolean,
    },
    status: {
        type: String,
    },
});

const form = useForm({
    email: "",
    password: "",
    remember: false,
});

const submit = () => {
    form.post(route("login"), {
        onFinish: () => form.reset("password"),
    });
};
</script>

<template>
    <GuestLayout>
        <Head title="Log in" />

        <div v-if="status" class="mb-4 font-medium text-sm text-green-600">
            {{ status }}
        </div>

        <form @submit.prevent="submit">
            <h1 class="text-2xl font-sans font-semibold text-gray-700">
                Login
            </h1>

            <hr class="mt-2 py-2 border-b-1 border-gray-300" />
            <div>
                <TextInput
                    id="email"
                    type="email"
                    class="mt-1 block w-full placeholder-gray-400"
                    v-model="form.email"
                    required
                    autofocus
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
                    autocomplete="current-password"
                    placeholder="Password"
                />

                <InputError class="mt-2" :message="form.errors.password" />
            </div>

            <div class="block mt-4">
                <label class="flex items-center">
                    <Checkbox name="remember" v-model:checked="form.remember" />
                    <span class="ms-2 text-sm text-gray-600">Remember me</span>
                </label>
            </div>
            <div class="text-center mt-6">
                <PrimaryButton
                    class="justify-center bg-indigo-600 text-white font-bold py-2 px-4 w-full rounded hover:bg-indigo-800"
                    :class="{ 'opacity-25': form.processing }"
                    :disabled="form.processing"
                >
                    Sign In
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
                    />Sign in with Google
                </button>
            </div>
            <div class="mt-7 flex items-center justify-between">
                <span class="border-b w-full lg:w-full"></span>

                <span class="border-b w-full lg:w-full"></span>
            </div>
            <div class="flex mt-4">
                <Link
                    v-if="canResetPassword"
                    :href="route('password.request')"
                    class="text-sm text-cyan-600 hover:text-cyan-900 rounded-md"
                >
                    Forgot your password?
                </Link>
            </div>
            <div class="flex text-sm text-gray-500">
                <a
                    >Don't have an account?
                    <Link
                        v-if="canResetPassword"
                        :href="route('register')"
                        class="text-sm text-cyan-600 hover:text-cyan-900 rounded-md"
                    >
                        Register here
                    </Link>
                </a>
            </div>
        </form>
    </GuestLayout>
</template>
