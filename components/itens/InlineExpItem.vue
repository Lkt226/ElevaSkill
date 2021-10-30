<template>
  <div class="experience" v-if="isNew === false">
      <span>
          <Linetext id="gitem" :text="company" divider="full"/>
          <h2 class="red">-</h2>
      </span>
      <Linetext id="gitem" :text="`${title} | ${startDate} - ${endDate}`" divider="full"/>
      <Linetext id="gitem" :text="description" divider="full"/>
  </div>
    <div class="experience" v-else>
        <span>
            <Linetext id="gitem" text="Nome da empresa" divider="full"/>
            <h2 class="green">+</h2>
        </span>
        <Linetext id="gitem" text="Seu cargo | 01/21 - 11/21" divider="full"/>
        <Linetext id="gitem" text="O que você fazia na empresa?" divider="full"/>
    </div>
</template>

<script>
export default {
    props: {
        isNew: {
            type: Boolean,
            default: false,
        },
        company: {
            type: String,
            default: '',
        },
        title: {
            type: String,
            default: '',
        },
        startDate: {
            type: String,
            default: '',
        },
        endDate: {
            type: String,
            default: '',
        },
        description: {
            type: String,
            default: '',
        },
    },
}
</script>

<style scoped>
.experience{
  @apply w-full mb-4;
}
.experience span{
  @apply flex w-full;
}
.green{
    @apply text-green-600;
}
.red{
    @apply text-red-600;
}
#gitem{
  width: 100%;
}
</style>