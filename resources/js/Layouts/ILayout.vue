<script setup>
import Nav from '@/Shared/Nav.vue';
import {computed} from "vue";
import {usePage} from "@inertiajs/vue3";

const theUserName = computed(() => usePage().props.auth.testuser);
</script>

<template>
    <div class="min-h-screen bg-gray-100 p-8 md:p-16">
        <Nav />
        <div class="max-w-xl mx-auto py-8">
            <p class="font-bold mb-4">Welcome back, {{ $page.props.auth.testuser }}!</p>
            <!-- could create a computed property to shorten the above reference -->
            <slot />
        </div>
    </div>
</template>
