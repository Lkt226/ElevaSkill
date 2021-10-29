<template>
  <div id="body">
      <Linetext text="Isto é um texto de linha."/>
      <DropText title="Notificações">
        <DefaultTextItem v-for="item in api" :key="item.id" 
          :text="item.name" :extra="item.extra" />
      </DropText>

      <DropText title="Cursos" path="/">
        <DefaultTextItem v-for="item in api" :key="item.id" 
          :text="item.name" :extra="item.extra" path="/"/>
      </DropText>

      <DropText title="Calendario" path="/">
        
      </DropText>
  </div>
</template>

<script>
export default {
  data() {
    return {
      api: [{name: "teste", extra: "teste"}]
    }
  }
}
</script>

<style>
*{
    font-family: 'Roboto', sans-serif;
    width: fit-content;
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}
html,body,#body, #__layout, #__nuxt{
    width: 100%;
    overflow: hidden;
}
</style>