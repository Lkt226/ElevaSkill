<template>
  <div class="background">
      <img src="../static/image.jpg" alt="foto de usuario" class="w-full">
      <section class="w-full hidden sm:block ">
          <span class="inline-item">
              <Linetext :text="name" divider="full"/>
              <Linetext :text="nickname || '+ Nome Social'" divider="full" class=" text-right"/>
          </span>
          <span class="inline-item">
              <Linetext :text="title" divider="full"/>
              <Linetext :text="birth" divider="full" class=" w-max"/>
          </span>
              <Linetext text="Resumo" divider="full"/>
              <h4>{{resume}}</h4>
     </section>
  </div>
</template>

<script>
export default {
    props: ['name', 'nickname', 'title', 'birth', 'resume'],
}
</script>

<style scoped>
.inline-item{
    @apply flex w-full justify-between items-end;
}

.background {
    @apply bg-black p-8 w-full;

    @media screen and (max-width: 1040px) {
        @apply sm:grid sm:grid-cols-2 sm:w-full;
    }

    @media (min-width: 1040px) {
        height: calc(100vh - 2rem);
        @apply max-w-sm relative m-4;
    }
}
.background * {
  @apply text-white;
}
</style>