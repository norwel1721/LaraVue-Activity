<!-- <script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head } from '@inertiajs/vue3';
</script>

<template>
    <Head title="Dashboard" />

    <AuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">Dashboard</h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                    <div class="p-6 text-gray-900">You're logged in!</div>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template> -->


<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head } from '@inertiajs/vue3'

defineProps({ users: Array })
</script>

<template>
  <AuthenticatedLayout>
    <Head title="Welcome" />
    <div class="container mx-auto">
        <div class="w-full lg:w-3/4 mx-auto">
            <div class="bg-white shadow-md rounded my-6">
            <table class="min-w-max w-full table-auto">
                <thead>
                <tr class="bg-gray-200 text-gray-600 uppercase text-sm leading-normal">
                    <th class="py-3 px-6 text-left">Name</th>
                    <th class="py-3 px-6 text-left">Email</th>
                    <th class="py-3 px-6 text-center">Email Verify</th>
                    <th class="py-3 px-6 text-center">Actions</th>
                </tr>
                </thead>
                <tbody class="text-gray-600 text-sm font-light">
                <tr v-for="(user, i) in users" :key="i" class="border-b border-gray-200 hover:bg-gray-100">
                    <td class="py-3 px-6 text-left whitespace-nowrap">{{ user.name }}</td>
                    <td class="py-3 px-6 text-left">{{ user.email }}</td>
                    <td class="py-3 px-6 text-center">{{ user.email_verified_at }}</td>
                    <td class="py-3 px-6 text-center">
                    <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded-full">
                        Edit
                    </button>
                    <button class="bg-red-500 hover:bg-red-700 text-white font-bold py-2 px-4 rounded-full">
                        Delete
                    </button>
                    </td>
                </tr>
                <!-- More rows can be added here -->
                </tbody>
            </table>
            </div>
        </div>
    </div>
  </AuthenticatedLayout>
</template>

