<template>
  <header class="header">
      <img class="profile-image" src="../static/image.jpg" alt="foto do usuario" />
      <menu>
        <ul class="menu-list">
          <li><img src="../static/History.svg" alt="" /></li>
          <li><img src="../static/Curriculum.svg" alt="" /></li>
          <li><img src="../static/avatar.svg" alt="" /></li>
          <li>
            <img class="menu-item-actived" src="../static/Eyes.svg" alt="" />
          </li>
        </ul>
      </menu>
    </header>
</template>

<script>
export default {

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
    .menu-item-actived {
        background-color: var(--color-blue);
    }

    .header {
        display: flex;
    }

    .profile-image {
        width: 80vw;
    }
</style>