<template>
  <div id="calendar">
        <h3>{{date}}</h3>
            <Divider size="full"/>
        <h4 class="pad">{{text}}</h4>
  </div>
</template>

<script>
export default {
    props: ['date', 'text'],
}
</script>

<style scoped>
.pad {
    padding-left: 0.5rem;
}
</style>