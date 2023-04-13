<script setup>
import debounce from "lodash/debounce";
import ILayout from '../../Layouts/ILayout.vue';
import Pagination from "@/Shared/Pagination.vue";
import { ref, watch } from "vue";
import { router } from "@inertiajs/vue3";

let props = defineProps({
    users: Object,
    filters: Object
});

let search = ref(props.filters.search);

watch(search, value => {
    router.get('/users', { search: value }, { preserveState: true, replace: true });
});
/*
watch(search, debounce(() => {
        router.get('/users', { search: value }, { preserveState: true, replace: true });
    },500)
)
*/
</script>

<script>
export default {
    layout: ILayout,
    components: {
        Pagination
    }
}
</script>

<template>
    <div>
        <Head title="Users" />
        <div>
            <div class="mb-2 flex flex-row items-center justify-between">
                <h1 class="text-2xl font-extrabold text-black">Users</h1>
                <Link href="users/create" class="text-blue-500 hover:text-blue-700 hover:font-bold">Create New User</Link>
                <input v-model="search" class="font-medium p-2 rounded-lg" type="text" placeholder="Search...." id="">
            </div>
            <div class="flex flex-col">
                <div class="-my-2 overflow-x-auto sm:-mx-6 lg:-mx-8">
                    <div class="py-2 align-middle inline-block min-w-full sm:px-6 lg:px-8">
                        <div class="shadow overflow-hidden border-b border-gray-200 sm:rounded-lg">
                            <table class="min-w-full divide-y divide-gray-200">
                                <tbody class="bg-white divide-y divide-gray-200">
                                <tr v-for="user in users.data" :key="user.id" class="hover:bg-blue-100">
                                    <td class="px-6 py-4 whitespace-nowrap">
                                        <div v-text="user.name" class="text-sm font-medium text-gray-900"></div>
                                    </td>
                                    <td class="px-6 py-4 whitespace-nowrap text-right text-sm font-medium">
                                        <Link :href="`/users/${user.id}/edit`" class="text-indigo-600 hover:text-indigo-900">Edit</Link>
                                    </td>
                                </tr>
                                </tbody>
                            </table>
                        </div>
                    </div>
                </div>
            </div>
            <div class="my-6">
                <Pagination :links="users.links" />
            </div>
        </div>
    </div>
</template>
