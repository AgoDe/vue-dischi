<template>
  <div id="app">
   
    <!-- header -->
    <!-- / header -->

    <!-- main -->
      <main-container
      :disks="disks"
      />
    <!-- / main -->

  </div>
</template>

<script>
import axios from 'axios'
import MainContainer from './components/MainContainer.vue'


export default {
  name: 'App',
  components: {
    MainContainer,
    
  },
  data() {
    return {
      disks: [],
    }
  },
  mounted() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((response) => {
      this.disks = response.data.response
      
    })
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Roboto', sans-serif;
}


</style>
