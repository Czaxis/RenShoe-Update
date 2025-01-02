<script setup>
import UserLayouts from './Layouts/UserLayouts.vue';

defineProps({
    orders: Array
})
</script>

<template>

    <UserLayouts>



        <div class="relative overflow-x-auto shadow-md sm:rounded-lg" style="max-width: 1200px; margin: 0 auto;">
            <table v-show="order.order_items.length > 0" v-for="order in orders" :key="order.id" class="w-auto text-sm text-left rtl:text-right text-gray-500 dark:text-gray-400"
                style="width: 100%;">
                <thead class="text-xs text-gray-700 uppercase dark:text-gray-400">
                    <tr>
                        <th scope="col" class="px-6 py-3 bg-gray-50 dark:bg-gray-800">
                            Order ID # {{ order.id }}
                        </th>

                    </tr>
                </thead>
                <tbody>
                    <tr v-for="item in order.order_items" :key="item.id" class="border-b border-gray-200 dark:border-gray-700">
                        <th scope="row"
                            class="px-6 py-4 font-medium text-gray-900 whitespace-nowrap bg-gray-50 dark:text-white dark:bg-gray-800">
                            {{item.product.product_name}}
                        </th>
                        <td class="px-6 py-4">
                            {{item.product.brand.name}}
                        </td>
                        <td class="px-6 py-4 bg-gray-50 dark:bg-gray-800">
                            {{item.product.category.name}}
                        </td>
                        <td class="px-6 py-4">
                            ${{item.product.price}}
                        </td>
                    </tr>
                    
                </tbody>
            </table>
        </div>





    </UserLayouts>


</template>