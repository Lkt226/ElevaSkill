<template>
    <div class="skill" v-if="isNew === false">
        <Linetext id="gitem" :text="title" divider="full"/>
        <h2 class="red">-</h2>
    </div>
    <div class="skill" v-else>
        <Linetext id="gitem" text="Novo item" divider="full"/>
        <h2 class="green">+</h2>
    </div>
</template>

<script>
export default {
    props: {
        title: {
            type: String,
            default: '',
        },
        isNew: {
            type: Boolean,
            default: false,
        },
    },
}
</script>

<style scoped>
    .skill {
        @apply flex w-full mb-1;
    }
    .green{
        @apply text-green-600;
    }
    .red{
        @apply text-red-600;
    }
    #gitem {
        width: 100%;
    }

</style>