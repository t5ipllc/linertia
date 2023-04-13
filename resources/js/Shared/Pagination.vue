<template>
    <Component
        :is="link.url ? 'Link' : 'span'"
        as="button"
        v-for="link in links"
        :disabled="link.active"
        :href="link.url"
        v-html="link.label"
        class="mx-2 mt-6 px-3 py-1 rounded-full bg-slate-700 text-white"
        :class="{ 'text-slate-100 bg-slate-500': ! link.url, 'font-bold bg-sky-800': link.active }"
    />

    <!-- the following does not work (IDK why)
    <Component
        :is="link.url ? 'Link' : 'span'"
        v-for="link in users.links"
        :href="link.url"
        v-html="link.label"
        class="px-1"
        :class="link.url ? '' : 'text-gray-500'"
        />
    -->

    <!-- the following works.
    <div class="mt-6" v-if="links.length > 3">
        <div class="flex flex-wrap -mb-1">
            <template v-for="(link, k) in links" :key="k">
                <div v-if="link.url === null"  class="mr-1 mb-1 px-4 py-3 text-sm leading-4 text-gray-400 border rounded" v-html="link.label" />
                <Link v-else class="mr-1 mb-1 px-4 py-3 text-sm leading-4 border rounded hover:bg-white focus:border-indigo-500 focus:text-indigo-500" :class="{ 'bg-blue-700 text-white': link.active }" :href="link.url" v-html="link.label" />
            </template>
        </div>
    </div>
    -->
</template>


<script>
export default {
    props: {
        links: Array,
    },
}
</script>
