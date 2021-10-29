<template>
    <div :class="notFull !== undefined ? 'fit' : 'w-full'">
      <h3>
      {{text}}{{extra !== undefined ? " - "+extra : ""}}
      </h3>
      <Divider :size="divider"/>
    </div>
</template>

<script>
export default {
  props:[
    'text',
    'extra',
    'divider',
    'notFull'
  ]
}
</script>

<style scoped>
.fit{
  width: fit-content;
}
</style>