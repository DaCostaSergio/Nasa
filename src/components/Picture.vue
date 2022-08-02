
<template>
  <div v-if="photo" class="">
    <a href="https://api.nasa.gov/">
      <img :src="photo.url" class="rounded-lg mt-10">
    </a>
  </div>
</template>

<script lang="js">
 export default  {
   name: 'pict',
   props: {
     photo: null
   },
   data () {
     return {

     }
   },
   created ()
   {

   },
   methods:
   {

   }
}

</script>
