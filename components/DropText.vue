<template>
    <div class="drop-text">
        <span>
            <NuxtLink :to="path" v-if="path !== ''">
                <h3>{{title}}</h3>
            </NuxtLink>
                
                <Linetext v-else :text="title" divider="none"/>

            <img @click="actived = !actived" :class="actived === true ? 'actived' : ''" 
            src="../static/open.svg" alt="open a page">
        </span>
       
        <Divider v-if="!main"/>
        <Divider v-else size="full"/>

        <ul :class="`list ${actived === false ? 'none' : ''}`" ><slot></slot></ul>
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
        },
        path: {
            type: String,
            default: ''
        },
        main: {
            type: Boolean,
            default: false
        }
    },
    data: function () {
        return {
            actived: true,
        }
    },
}
</script>

<style scoped>
.drop-text {
    padding-left: 0.5rem;
    width: calc(100% - 0.5rem);
}
.drop-text > span {
    display: flex;
    justify-content: space-between;
    width: 100%;
    text-align: left;
}
.list {
    padding-left: 0.5rem;
    width: 100%;
}
.go-to-page {
    transform: rotate(-90deg);
}
.actived {
    transform: rotate(180deg);
}
.none {
    display: none;
}
</style>