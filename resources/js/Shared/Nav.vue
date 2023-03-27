<template>
    <nav class="px-12 h-12 bg-gray-200 flex items-center gap-x-4">
        <NavLink href="/" :active="$page.component === 'Home'">Home</NavLink>
        <NavLink href="/users" :active="$page.component === 'Users'">Users</NavLink>
        <NavLink href="/settings" :active="$page.component === 'Settings'">Settings</NavLink>
        <Link href="/frogout" method="post" as="button">Logout</Link>
    </nav>
</template>

<script setup>
import NavLink from '../Shared/NavLink.vue';

</script>
