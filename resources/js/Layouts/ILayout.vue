<script setup>
import Nav from '@/Shared/Nav.vue';
import {computed} from "vue";
import {usePage} from "@inertiajs/vue3";

const theUserName = computed(() => usePage().props.auth.testuser);
</script>

<template>
    <div class="min-h-screen bg-gray-100 p-8 md:p16 border border-8 border-blue-800">
        <p class="font-bold text-red-900 -ml-8 -mt-8 mb-8">Layouts/ILayout.vue</p>
        <Nav />
        <div class="py-8">
            <p class="font-bold mb-4">Welcome back, {{ $page.props.auth.testuser }}!</p>
            <!-- could create a computed property to shorten the above reference -->
            <slot />
        </div>
    </div>
</template>
