<template>
    <div v-if="size === 'full'" class="divider full"/>
    <div v-else-if="size === 'none'" class="divider none"/>
    <div v-else class="divider"/>

</template>

<script>
export default {
    props:{
        size: {
            type: String,
            default: 'normal'
        },
    }
}
</script>

<style scoped>
.divider {
    border-top: 1px solid #c4c4c4;
    width: calc(100% + 1rem);
}
.full {
    width: 100%;
}
.none {
    display: none;
}
</style>