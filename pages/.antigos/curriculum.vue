<template>
  <div class="body">
      <Perfil img="" actived="2"/>
        <div id="social-info">
          <h3 class="c-gray" style="padding-left: 1rem;" >+ Nome social</h3>
          <h3 style="padding-left: 1rem;" >{{curriculum.name}}</h3>
          <Divider type="m" pad="0"/>
          <h3 style="padding-left: 1rem;" >{{curriculum.title}}</h3>
          <Divider type="m" pad="0"/>
          <h3 style="padding-left: 1rem;" >{{curriculum.birth}}</h3>
          <Divider type="m" pad="1"/>
        <br>
        </div>
        
        <LineList type="test" text="Testes" :api="test" extra="score"/>
        <br>
        
        <div id="gender-race-status">
          <h3 style="padding-left: 1rem;" >Gênero: {{curriculum.gender}}</h3>
          <Divider type="m" pad="0"/>
          <h3 style="padding-left: 1rem;" >Raça: {{curriculum.race}}</h3>
          <Divider type="m" pad="0"/>
          <h3 style="padding-left: 1rem;" >Estado Civil: {{curriculum.civil_status}}</h3>
          <Divider type="m" pad="1"/>
          <br>
        </div>

        <div id="endress" class="endress">
          <h3 style="padding-left: 1rem;" >País: {{curriculum.country}}</h3>
          <Divider type="m" pad="0"/>
          <h3 style="padding-left: 1rem;" >Estado: {{curriculum.state}}</h3>
          <Divider type="m" pad="0"/>
          <h3 style="padding-left: 1rem;" >Endereço: {{curriculum.endress}}</h3>
          <Divider type="m" pad="0"/>
          <h3 style="padding-left: 1rem;" >CEP: {{curriculum.zip_code}}</h3>
          <Divider type="m" pad="1"/>
          <br>
        </div>

        <LineExperience title="Experiência profissional" type="experience" :api="experience"/>
        <br>
        <LineExperience title="Perfil acadêmico" type="education" :api="education"/>
        <br>

        <LineSkills type="soft" text="Soft Skills" :api="soft_skills"/>
        <br>
        <LineSkills type="hard" text="Hard Skills" :api="hard_skills"/>
        <br>
        <LineList type="plataform" text="Partificapão na plataforma" :api="plataform_historic"/>
        <br>

        <div id="contact">
          <h3 style="padding-left: 1rem;" >Telefone: {{curriculum.phone}}</h3>
          <Divider type="m" pad="0"/>
          <h3 style="padding-left: 1rem;" >Email: {{curriculum.email}}</h3>
          <Divider type="m" pad="0"/>
          <br>
        </div>

        <LineList type="social_media" text="Redes sociais" :api="social_media" extra="user"/>
        <br>
        <LineList type="about_comments" text="Comentarios sobre:" :api="about_comments" extra="user"/>
        <br>
  </div>
</template>

<script>
import { api } from '../../backend/API.js'
export default {
  data(){
    return{
      curriculum: api.curriculum,
      test: api.curriculum.comportament_test,
      soft_skills: api.curriculum.soft_skills,
      hard_skills: api.curriculum.hard_skills,
      social_media: api.curriculum.social_media,

      experience: api.curriculum.experience,
      education: api.curriculum.education,

      plataform_historic: api.plataform_historic,
      about_comments: api.about_comments,
    }
  }
}
</script>

<style scoped>
  
</style>