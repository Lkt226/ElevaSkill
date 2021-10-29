<template>
  <div id="body" class="flex flex-col lg:flex-row">
    <Menu :actived="3"/>
    <Profile :name="name" :title="curriculum.title" :birth="curriculum.birth" :resume="curriculum.resume"/>
    <main class="w-full grid sm:grid-cols-2">
        <DropText title="Historico de participações" class="p-2" main>
            <DropText v-for="historic in parties_historic" :key="historic.id" :title="historic.date" main>
                <Linetext v-for="item in historic.itens" :text="item.name" :key="item.id" divider="full"/>
            </DropText>
        </DropText>
        
        <DropText title="Historico da plataforma" class="p-2" main>
            <DropText v-for="historic in plataform_historic" :key="historic.id" :title="historic.date" main>
                <Linetext v-for="item in historic.itens" :text="item.name" :key="item.id" divider="full"/>
            </DropText>
        </DropText>
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

        plataform_historic: api.plataform_historic,
        parties_historic: api.parties_historic,
      
    }
  }
}
</script>

<style>

</style>