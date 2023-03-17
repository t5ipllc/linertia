<template>
    <div>
        <h1 class="text-3xl font-extrabold text-black">Hello, {{ name }}!</h1>
    </div>
    <p>In this series, we'll use the following frameworks:</p>
    <ol>
        <li v-for="fw in frameworks">{{ fw }}</li>
    </ol>
</template>

<script setup>
defineProps({
    name: String,
    frameworks: Array
});
</script>