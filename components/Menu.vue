<template>
    <menu class="menu" v-if="$device.isMobile">
        <ul class="flex">
            <li v-for="item in items" :key="item.id" :class="`item ${item.id === actived ? 'actived': ''}`">
                <NuxtLink :to="item.href">
                    <img :src="item.icon" :alt="'Ir para '+item.text">
                </NuxtLink>
            </li>
        </ul>
    </menu>
    
    <menu class="menu" v-else>
        <ul class="flex" v-if="open === true" @mouseleave="open=false">
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
            default: false
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
                { text: 'Curriculum', href: '/curriculum', icon: require('../static/Curriculum.svg'), id:1},
                { text: 'Avatar', href: '/avatar', icon: require('../static/avatar.svg'), id:2},
                { text: 'Historic', href: '/historic', icon: require('../static/History.svg'), id:3},
            ]
        }
    }
}
</script>

<style scoped>
    .menu {
        @apply fixed left-0  p-0 m-0 z-50;
        @media screen and (max-width: 640px) {
            @apply fixed bottom-0 flex flex-col justify-end w-full h-auto z-50;
        }
    }
    .item{
        @apply w-16 h-16 bg-black;
        @media screen and (max-width: 640px) {
            @apply w-1/4;
        }
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