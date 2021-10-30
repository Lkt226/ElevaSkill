<template>
  <div id="body" class="flex flex-col lg:flex-row">
    <Menu :actived="2"/>
    <Profile :name="name" :title="curriculum.title" :birth="curriculum.birth" :resume="curriculum.resume"/>
    <main class="w-full grid grid-cols-2">
      <div id="avatar" class="w-full flex justify-center">
        <AvatarHead class="absolute" :TopSize="5" :BottomSize="0" Gender="male" Color="#E9CFB8"/>
        <img class="absolute" v-for="item in avatar.face" :key="item.id"
          :src="item.path" alt="Parte do rosto do avatar">
      </div>

      <div>
        
      </div>
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

      avatar: api.avatar
    }
  }
}
</script>

<style scoped>

</style>