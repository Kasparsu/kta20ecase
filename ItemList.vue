<template>
    <div>
        <h1 class="is-size-1">{{title}}</h1>
        <ul>
            <li v-for="item in items" :key="item.key">
                <input type="checkbox" v-model="item.isDone">
                {{ item.name }}
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: "ItemList",
        props: ['title', 'items']
    }
</script>

<style scoped>

</style>