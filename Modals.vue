<template>
    <modal :open="open"></modal>
</template>

<script>
    import Modal from "./Modal";
    export default {
        name: "Modals",
        components: {Modal},
        props: ['open']
    }
</script>

<style scoped>

</style>