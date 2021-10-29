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
        display: flex;
        width: 100%;
    }
    .green{
        color: #00ff00;
    }
    .red{
        color: #ff0000;
    }
    #gitem {
        width: 100%;
    }

</style>