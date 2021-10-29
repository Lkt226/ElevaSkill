<template>
    <div :class="`divider ${size}`"/>
</template>

<script>
export default {
    props:{
        size: {
            type: String,
            default: ''
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