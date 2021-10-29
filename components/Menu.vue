<template>
    <menu>
        <ul class="menu" v-if="open === true" @mouseleave="open=false">
            <li v-for="item in items" :key="item.id" :class="`item ${item.id === actived ? 'actived': ''}`">
                <NuxtLink :to="item.href">
                    <img :src="item.icon" :alt="'Ir para '+item.text">
                </NuxtLink>
            </li>
        </ul>
        <div class="item actived" v-else @mouseenter="open=true">
            <img :src="items[actived].icon" :alt="'Ir para '+items[actived].text">
        </div>
    </menu>
    
</template>

<script>
export default {
    props: {
        isOpen: {
            type: Boolean,
            default: true
        },
        actived: {
            type: Number,
            default: 0
        },
    },
    data() {
        return {
            open: this.isOpen,
            items: [
                { text: 'Home', href: '/', icon: require('../static/Eyes.svg'), id:0 },
                { text: 'Curriculum', href: '/about', icon: require('../static/Curriculum.svg'), id:1},
                { text: 'Avatar', href: '/contact', icon: require('../static/avatar.svg'), id:2},
                { text: 'Historic', href: '/contact', icon: require('../static/History.svg'), id:3},
            ]
        }
    }
}
</script>

<style scoped>
    .menu {
        display: flex;
    }
    .item{
        width: 50px;
        height: 50px;
        background: #000;
    }
    .item > *{
        width: 100%;
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .actived{
        background: blue;
    }

</style>