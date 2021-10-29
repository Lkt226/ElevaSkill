<template>
  <header class="header">
    <img class="profile-image" :src="profileImg" alt="foto do usuario" />
    <menu>
      <ul class="menu-list">
        <NuxtLink to="/historic">
          <img :class="actived1" src="../static/History.svg" alt="Historico de atividades" />
        </NuxtLink>

        <NuxtLink to="/curriculum">
          <img :class="actived2" src="../static/Curriculum.svg" alt="curriculo" />
        </NuxtLink>

        <NuxtLink to="/avatar">
          <img :class="actived3" src="../static/avatar.svg" alt="avatar" />
        </NuxtLink>
        
        <NuxtLink to="/">
          <img :class="actived4" src="../static/Eyes.svg" alt="home" />
        </NuxtLink>
      </ul>
    </menu>
  </header>
</template>

<script>
export default {
  props: ['img', 'actived'],
  data() {
    return {
      profileImg : require('../static/image.jpg'),
      actived1: this.actived === '1' ? 'actived' : '',
      actived2: this.actived === '2' ? 'actived' : '',
      actived3: this.actived === '3' ? 'actived' : '',
      actived4: this.actived === '4' ? 'actived' : '',
    }
  }
}
</script>
<style scoped>
    .menu-list * {
        background-color: var(--color-black);
        width: 20vw;
        height: 20vw;
    }
    .menu-list * > * {
        padding: 1rem;
    }
    .actived {
        background-color: var(--color-blue);
    }

    .header {
        display: flex;
    }

    .profile-image {
        width: 80vw;
    }
</style>