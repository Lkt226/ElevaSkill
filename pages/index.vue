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
        <InlineCalendarItem date="15/10/12" text="Eu sou um teste de calendario, feito em VueJS"/>
      </DropText>

      <DropText title="Vagas" path="/">
        <InlineJobsItem title="Teste" date="10/12" company="Microsoft" nivel="Junior"/>
      </DropText>

      <DropText title="Historico">
        <DropText title="16/11/21" :main="true">
          <h4>Eu sou um teste de calendario, feito em VueJS</h4>
        </DropText>
      </DropText>

      <DropText title="Historico profissional">
        <InlineExpItem company="Microsoft" title="Web developer" startDate="10/12" endDate="11/12" description="Cria aplicações web para a microsoft"/>
        <InlineExpItem isNew/>
      </DropText>

      <DropText title="HardSkills">
        <InlineSkillItem title="Skill 1"/>
        <InlineSkillItem isNew/>
      </DropText>

      <Menu/>

      <Profile name="Margarete de Souza" title="Analista de marketing Junior" birth="29/12/1989" resume="Margarete é uma pessoa"/> 

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
    overflow-x: hidden;
}
</style>