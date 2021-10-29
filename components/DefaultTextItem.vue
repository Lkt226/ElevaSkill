<template>
    <li class="item">
        <Linetext :text="text" :extra="extra" divider="none"/>
        
        <NuxtLink  v-if="path !== undefined" :to="'/'+path"> <img class="button" src="../static/open.svg" alt="open a page"></NuxtLink>
        <img v-else class="none" src="../static/open.svg" alt="open a page">
        
        <Divider/>
    </li>
</template>

<script>
export default {
    props: {
        text: {
            type: String,
            required: true
        },
        extra: {
            type: String,
            required: false
        },
        path: {
            type: String,
            required: false
        }
    }
}
</script>

<style scoped>
.item {
    display: grid;
    grid-template-columns: 1fr auto;

    justify-content: space-between;
    align-items: center;

    width: 100%;
}
.button {
    transform: rotateZ(-90deg);
}
.none {
    opacity: 0;
}
</style>