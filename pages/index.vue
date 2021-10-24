<template>
  <div class="body">
    <Perfil img=""/>

    <h3>Meu perfil</h3>
    <Divider type="l" pad="1"/>

    <LineList type="notification" text="Visitaram seu perfil" :api="notification"/>
    <LineList type="courses" text="Cursos em andamento" :api="courses"/>
    <br>
    <h3>Calendario</h3>
    <Divider type="l" pad="1"/>
    <Calendar :api="calendar"/>

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
      calendar: api.calendar
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
