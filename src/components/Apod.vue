<template>
  <section>
    <div class="">
      <img v-if="item" :src="item.url" height="500">
    </div>
  </section>


</template>

<script lang="js">

import axios from 'axios'
const baseURL =  'http://localhost:8000';
const client = axios.create({
  baseURL: baseURL
});


 export default  {
   name: 'apod',
   props: {},
   components: {

   },
   data () {
     return {
       item: null
     }
   },

   created ()
   {
     this.loadImages()
   },

   methods:
   {

     loadImages()
     {
       client.get('apod', {
         params: {
           url:'',
           date:'',
           // api_key: import.meta.env.VITE_APP_KEY
         }
       })
       .then(this.successHandler)
       .catch(this.errorHadnler)
     },

     successHandler(res)
     {
       console.log(res.data)
       this.item = res.data.data
       // console.log('yes sir');
       // console.log(this.item.url)

     },

     errorHandler(res)
     {
       console.log(res);
     }
   },
}

</script>

<style>



</style>
