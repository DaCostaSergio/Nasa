<template>

  <a href="https://api.nasa.gov/">
    <button class="" type="button"  name="button">link for API</button>
  </a>

  <section class="">
    <pict v-for="item in items" :photo="item"  />
  </section>
</template>

<script lang="js">
import Pict from './Picture.vue'
import axios from 'axios'
const baseURL =  'http://127.0.0.1:8000/';
const client = axios.create({
  baseURL: baseURL
});

 export default  {
   name: 'library',
   props: {},
   components: {
     pict: Pict
   },
   data () {
     return {
       items: []
     }
   },

   created ()
   {
     console.log(this.items);
     this.loadImages()
   },

   beforeMount()
   {
     console.log('beforeMount');
   },

   methods:
   {

     loadImages()
     {
       client.get('curiosity', {
         params: {
           sol: '1000',
           // api_key: import.meta.env.VITE_APP_KEY
         }
       })
       .then(this.successHandler)
       .catch(this.errorHadnler)

       console.log('yo');
     },

     successHandler(res)
     {
       console.log(res.data)
       this.items = res.data.data
       // console.log(this.items);
     },

     errorHadnler(res)
     {
       console.log(res);
     }
   },
}

</script>
