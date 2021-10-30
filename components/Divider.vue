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
    @apply border-t border-gray-300 border-solid;
}
.full {
    @apply w-full;
}

.none {
    @apply hidden;
}
</style>