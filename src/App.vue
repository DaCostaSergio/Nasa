


<script>
import Home from './components/Home.vue'
import Library from './components/Library.vue'
import Apod from './components/Apod.vue'


const routes = {
  '/': Home,
  '/library': Library,
  '/apod':Apod

}

export default {
  data() {
    return {
      currentPath: window.location.hash
    }
  },
  computed: {
    currentView() {
      return routes[this.currentPath.slice(1) || '/']
    }
  },
  mounted() {
    window.addEventListener('hashchange', () => {
		  this.currentPath = window.location.hash
		})
  }
}
</script>

<template>
  <div class="bg-black text-white flex justify-around outline-blue-500  ">
    <a href="#/">Home</a> |
    <a href="#/library">Library</a> |
    <a href="#/apod">Apod</a>

  </div>

  <component :is="currentView" />
</template>
