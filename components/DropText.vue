<template>
    <div class="drop-text">
        <span class="flex justify-between w-full text-left">
            <NuxtLink :to="path" v-if="path !== ''">
                <h3>{{title}}</h3>
            </NuxtLink>
                <h3>{{title}}</h3>
                
            <img @click="actived = !actived" :class="actived === true ? 'actived' : ''" 
            src="../static/open.svg" alt="open a page">
        </span>
       
        <Divider v-if="!main"/>
        <Divider v-else size="full"/>

        <ul :class="`pl-2 w-full ${actived === false ? 'none' : ''}`" ><slot></slot></ul>
    </div>
</template>

<script>
export default {
    props: {
        title: {  /// title of the dropdown
            type: String,
            default: 'Dropdown'
        },
        path: { /// What path to go to
            type: String,
            default: ''
        },
        main: { /// if it is the main dropdown -> main line have less divisor size
            type: Boolean,
            default: false
        }
    },
    data: function () {
        return { /// if it is actived -> show the list
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

.actived {
    transform: rotate(180deg);
    @apply rotate-180;
}
.none {
    @apply hidden;
}
</style>