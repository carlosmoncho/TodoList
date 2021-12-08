<template>
    <li>
        <input type="checkbox" v-model="item.done">
        <del v-if="item.done">
            {{ item.descrip }}
        </del>
        <span v-else>
            {{ item.descrip }}
        </span>             
    </li>
</template>

<script>
export default {
    name: 'todo-item',
    props: ['item'],
}
</script>