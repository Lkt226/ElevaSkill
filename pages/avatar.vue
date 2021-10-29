<template>
  <div id="body" class="flex flex-col lg:flex-row">
    <Menu :actived="2"/>
    <Profile :name="name" :title="curriculum.title" :birth="curriculum.birth" :resume="curriculum.resume"/>
    <main class="w-full grid sm:grid-cols-2">
      <section id="left-side" class="p-2">
       
      </section>
      <section id="right-side" class="p-2">
    
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
      
    }
  }
}
</script>

<style>

</style>