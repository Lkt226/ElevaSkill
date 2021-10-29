<template>
  <div class="body">
    <Perfil img="" actived="4"/>

    <h3 style="padding-left: 0.5rem;" >Meu perfil</h3>
    <Divider type="l" pad="1"/>

    <LineList type="notification" text="Visitaram seu perfil" :api="notification" extra="date"/>
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
import { api } from '../../backend/API.js'
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
    --color-red: #f29c9c;
  }

  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    list-style-type: none;
  }
  html,
  body,
  #__nuxt,
  .body {
    width: 100vw;
    overflow-x: hidden;
  }

  h3{
    padding: 1rem 0 0 0;
  }

  .c-gray{
    color: var(--color-gray);
  }
  .c-red{
    color: var(--color-red);
  }
  .c-green{
    color: var(--color-green);
  }
</style>
