<template>
    <div class="drop-text">
        <Linetext :text="title" divider="none"/>
        <img src="../static/open.svg" alt="open a page">
        <Divider size="full"/>
        <ul class="list"><slot></slot></ul>
    </div>
</template>

<script>
export default {
    props: {
        title: {
            type: String,
            default: 'Dropdown'
        },
        api: {
            type: String,
            default: ''
        }
    },
    data: function () {
        return {
            actived: false,
        }
    },
}
</script>

<style scoped>
.drop-text {
    display: grid;
    grid-template-columns: 1fr 1fr;
    padding-left: 0.5rem;
    width: calc(100vw - 0.5rem);
}
.list {
    padding-left: 0.5rem;
    width: 100%;
}
</style>