<template>
    <div class="body">
        <Perfil img="" actived="1"/>
        <LineDate title="Historico de participações" type="parts" :api="parties_historic"/>
        <br>

        <LineDate title="Historico de atividades na plataforma" type="activities" :api="plataform_historic"/>
        <br>
    </div>
</template>

<script>
import { api } from '../backend/API.js'
export default {
  data(){
    return{
      plataform_historic: api.plataform_historic,
      parties_historic: api.parties_historic,
    }
  }
}
</script>

<style>

</style>