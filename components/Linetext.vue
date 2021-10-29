<template>
    <div class="line">
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
    'divider'
  ]
}
</script>

<style scoped>
.line{
  width: fit-content;
}
</style>