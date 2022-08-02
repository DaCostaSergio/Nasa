<template>
  <header class="mt-20 ml-20 flex flex-row items-center text-white">

    <div class="">
      <img alt="Vue logo" class="logo" src="../assets/nasa-6.svg" width="125" height="125" />
    </div>
    <div class="basis-1/4 ml-12">
      <my-title msg="STAGE CHEZ WGR" class="font-medium text-green"/>
    </div>

    <div class="flex">
      <div class="text-7xl mt-10">
        Récupération de données de l'API de la NASA via Laravel
        Affichage des données via Vuejs 3
      </div>
    </div>
  </header>

</template>

<script lang="js">
 import Title from './Title.vue'
 // import Roller from 'vue-roller'

 export default {
   components: {
     'my-title': Title,

   }
 }
</script>
