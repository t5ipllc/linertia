<script setup>
import ILayout from '../Layouts/ILayout.vue';
import Pagination from "@/Shared/Pagination.vue";

defineProps({
    users: Array
});
</script>

<script>
export default {
    layout: ILayout
}
</script>

<template>
    <div>
        <Head title="Users" />
        <div>
            <h1 class="mb-2 text-2xl font-extrabold text-black">Users</h1>
            <div class="flex flex-col">
                <div class="-my-2 overflow-x-auto sm:-mx-6 lg:-mx-8">
                    <div class="py-2 align-middle inline-block min-w-full sm:px-6 lg:px-8">
                        <div class="shadow overflow-hidden border-b border-gray-200 sm:rounded-lg">
                            <table class="min-w-full divide-y divide-gray-200">
                                <tbody class="bg-white divide-y divide-gray-200">
                                <tr>
                                    <td class="px-6 py-4 whitespace-nowrap">
                                        <div class="text-sm font-medium text-gray-900">Jane Cooper</div>
                                    </td>
                                    td.
                                </tr>
                                </tbody>
                            </table>
                        </div>
                    </div>
                </div>
            </div>






            <ul>
                <li v-for="user in users" :key="user.id" v-text="user.name"></li>
            </ul>
        </div>
    </div>
</template>
