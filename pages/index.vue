<template>
  <div id="body">
    <Menu class=""/>
    <Profile :name="name" :title="curriculum.title" :birth="curriculum.birth" :resume="curriculum.resume"/>
    <main class="grid sm:grid-cols-2">
      <section id="left-side" class="p-2">
        <DropText id="notification" title="Visitaram o seu perfil" main>
          <Linetext v-for="item in notification" :key="item.id" class="w-full"
            :text="item.name" :extra="item.date" divider="full"/>
        </DropText>
      </section>


    </main>
  </div>
</template>

<script>
import {api} from '../assets/service/API'
export default {
  data() {
    return {
      name: api.curriculum.name,
      curriculum: api.curriculum,
      notification: api.notification
    }
  }
}
</script>

<style>

</style>