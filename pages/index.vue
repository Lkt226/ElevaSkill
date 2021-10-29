<template>
  <div id="body" class="flex flex-col lg:flex-row">
    <Menu class=""/>
    <Profile :name="name" :title="curriculum.title" :birth="curriculum.birth" :resume="curriculum.resume"/>
    <main class="w-full grid sm:grid-cols-2">
      <section id="left-side" class="p-2">
        <DropText id="notification" title="Visitaram o seu perfil" main>
          <Linetext v-for="item in notification" :key="item.id" class="w-full"
            :text="item.name" :extra="item.date" divider="full"/>
        </DropText>

        <DropText id="Courses" title="Cursos em andamento" main>
          <DefaultTextItem v-for="item in courses" :key="item.id" class="w-full"
            :text="item.name" path="/" divider="full"/>
        </DropText>

        <DropText id="Jobs" title="Vagas" main>
          <InlineJobsItem v-for="item in jobs" :key="item.id" class="w-full"
            :title="item.name" :company="item.company" :date="item.createDate" 
            :seniority="item.seniority" path="/" divider="full"/>
        </DropText>
      </section>
      <section id="right-side" class="p-2">
        <Map/>

        <DropText id="calendar" title="Calendario" main>
          <InlineCalendarItem v-for="item in calendar" :key="item.id" class="w-full"
            :text="item.event" :date="item.date" path="/" divider="full"/>
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
      notification: api.notification,
      courses: api.courses,
      jobs: api.jobs,
      calendar: api.calendar
    }
  }
}
</script>

<style>

</style>