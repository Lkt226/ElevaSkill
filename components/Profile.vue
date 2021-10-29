<template>
  <div class="background">
      <img src="../static/image.jpg" alt="foto de usuario" class="user-img">
      <section id="personal-information">
          <span class="inline-between">
              <Linetext :text="name" divider="full"/>
              <Linetext :text="nickname || '+ Nome Social'" divider="full"/>
          </span>
          <span class="inline-between">
              <Linetext :text="title" divider="full"/>
              <Linetext :text="birth" divider="full"/>
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
.inline-between{
    display: flex;
    width: 100%;
    justify-content: space-between;
    align-items: flex-end;
}
#personal-information{
    width: 100%;
}
.background {
  width: 50vw;
  padding: 2rem;
  background: black;
}
.background * {
  color: white;
}

.user-img{
    width: 100%;
    height: auto;

}
</style>