<template>
  <div class="body">
    <Perfil img="" actived="4"/>

    <h3 style="padding-left: 0.5rem;" >Meu perfil</h3>
    <Divider type="l" pad="1"/>

    <LineList type="notification" text="Visitaram seu perfil" :api="notification"/>
    <LineList type="courses" text="Cursos em andamento" :api="courses"/>
    
    <br>

    <LineCalendar :api="calendar"/>

    <br>
    
    <h3 style="padding-left: 0.5rem;" >Empresas na área</h3>
    <Divider type="l" pad="1"/>
    <Map/>

    <br>
    
    <LineJobs :api="jobs"/>

    <br>
    <br>
  </div>
</template>

<script>
import { api } from '../backend/API.js'
console.log(api)
export default {
  data(){
    return{
      notification: api.notification,
      courses: api.courses,
      calendar: api.calendar,
      jobs: api.jobs
    }
  }
}
</script>

<style>
  :root {
    --color-black: #4e4e4e;
    --color-gray: #c4c4c4;
    --color-white: #ffffff;
    --color-blue: #84c4f2;
    --color-green: #a3c992;
  }

  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    list-style-type: none;
  }
  html,
  body,
  .body {
    width: 100vw;
  }

  h3{
    padding: 1rem 0 0 0;
  }

  .c-gray{
    color: var(--color-gray);
  }
</style>
