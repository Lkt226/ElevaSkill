<template>
  <div id="body" class="flex flex-col lg:flex-row">
    <Menu :actived="1" class=""/>
    <Profile :name="name" :title="curriculum.title" :birth="curriculum.birth" :resume="curriculum.resume"/>
    <main class="w-full grid sm:grid-cols-2">
        <div id="inMobile" class="p-4" v-if="$device.isMobile">
            <span class="inline-item">
              <Linetext :text="name" divider="full"/>
              <Linetext :text="curriculum.nickname || '+ Nome Social'" divider="full" class=" text-right"/>
            </span>
            <span class="inline-item">
              <Linetext :text="curriculum.title" divider="full"/>
              <Linetext :text="curriculum.birth" divider="full" class=" w-max"/>
            </span>
              <Linetext text="Resumo" divider="full"/>
              <h4>{{curriculum.resume}}</h4>
        </div>
      <section id="left-side" class="p-2">
        <DropText title="Testes" main>
            <DefaultTextItem v-for="item in comportament_test" :key="item.id"
                :text="item.name + ' - ' + item.score" path="/"/>
        </DropText>

        <Linetext :text="'Gênero: '+curriculum.gender" divider="full" class=" px-2"/>
        <Linetext :text="'Raça: '+curriculum.race" divider="full" class="px-2"/>
        <Linetext :text="'Estado Civil: '+curriculum.civil_status" divider="full" class="px-2"/>
        <br>
        <span class=" flex w-full">
            <Linetext :text="curriculum.country" divider="full" class="px-2"/>
            <Linetext :text="curriculum.state" divider="full" class="px-2"/>
        </span>
        <Linetext :text="curriculum.endress" divider="full" class="px-2"/>
        <br>
        <Linetext :text="'Telefone: '+curriculum.phone" divider="full" class="px-2"/>
        <Linetext :text="'E-mail: '+curriculum.email" divider="full" class="px-2"/>
        <br>
        <DropText title="Redes sociais" main>
            <DefaultTextItem v-for="item in social_media" :key="item.id"
                :text="item.name" :extra="item.user" :path="item.path"/>
        </DropText>
    
        <DropText title="Comentarios de orientadores" main>
            <DefaultTextItem v-for="item in about_comments" :key="item.id"
                :text="`${item.owner}: '${item.name}'`" :extra="item.date" :path="item.path"/>
        </DropText>
      </section>
      <section id="right-side" class="p-2">
        <DropText title="Soft Skills" main>
            <InlineSkillItem v-for="item in soft_skills" :key="item.id"
                :title="item.name+' - '+item.test"/>
            <InlineSkillItem isNew/>
            
        </DropText>

        <DropText title="Hard Skills" main>
            <InlineSkillItem v-for="item in hard_skills" :key="item.id"
                :title="item.name+' - '+item.test"/>
            <InlineSkillItem isNew/>
            
        </DropText>

        <DropText title="Experiência profissional" main>
            <InlineExpItem v-for="item in experience" :key="item.id"
                :company="item.name" :title="item.title" :startDate="item.start_date"
                :endDate="item.end_date" :description="item.description"/>
            <InlineExpItem isNew/>
          
        </DropText>

        <DropText title="Formação acadêmica" main>
            <InlineExpItem v-for="item in education" :key="item.id"
                :company="item.name" :title="item.title" :startDate="item.start_date"
                :endDate="item.end_date" :description="item.description"/>
            <InlineExpItem isNew/>
    
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
        comportament_test: api.curriculum.comportament_test,
        social_media: api.curriculum.social_media,
        plataform_historic: api.plataform_historic,
        about_comments: api.about_comments,

        soft_skills: api.curriculum.soft_skills,
        hard_skills: api.curriculum.hard_skills,
        experience: api.curriculum.experience,
        education: api.curriculum.education,
    }
  }
}
</script>

<style scoped>
.inline-item{
    @apply flex w-full justify-between items-end;
}
</style>