<template>
    <nav class="px-12 h-12 bg-gray-200 flex items-center gap-x-4">
        <Link href="/">Home</Link>
        <Link href="/users">Users</Link>
        <Link href="/settings">Settings</Link>
    </nav>
</template>

<script setup>
import { Link } from '@inertiajs/vue3';

</script>