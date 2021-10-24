<template>
  <div v-if="type == 'l'" class="divider large"></div>
  <div v-else-if="type == 'm'" class="divider medium"></div>
  <div v-else-if="type == 's'" class="divider small"></div>
  <div v-else class="divider"></div>
</template>

<script>
export default {
    props:['type']
}
</script>

<style scoped>
    .divider{
        background-color: var(--color-black);
        height: 1px;

        position: relative;
        left: 50%;
        transform: translate(-50%, 0);
    }

    .large{
        width: 100%;
    }
    .medium{
        width: 90%;
    }
    .small{
        width: 80%;
    }
</style>