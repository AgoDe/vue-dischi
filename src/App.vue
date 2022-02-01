<template>
  <div id="app">
   
    <!-- header -->
    <header-container
    @genreFilter="filterByGenre"
    @artistFilter="filterByArtist"
    :genre="musicalGenre"
    :artists="musicalArtists"
    />
    <!-- / header -->

    <!-- main -->
      <main-container
      :disks="generalFilter"
      />
    <!-- / main -->

  </div>
</template>

<script>
import axios from 'axios'
import MainContainer from './components/MainContainer.vue';
import HeaderContainer from './components/HeaderContainer.vue';


export default {
  name: 'App',
  components: {
    MainContainer,
    HeaderContainer,
    
  },
  data() {
    return {
      disks: [],
      disksSelected: [],
      musicalGenre: [],
      musicalArtists: [],
      generalFilter: [],
      
    }
  },
  methods: {
    filterByGenre: function(selected) {

      this.disksSelected = this.disks.filter((element) => {
        return element.genre.includes(selected)
      })
      this.generalFilter = this.disksSelected;
      const artistArray = this.disksSelected.map((element) => {
        return element.author
      })
      this.musicalArtists = [...new Set(artistArray)];


      
    },

    filterByArtist: function(selected) {

      this.generalFilter = this.disksSelected.filter((element) => {
        return element.author.includes(selected)
      })
    },
  },
  mounted() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((response) => {
      this.disks = response.data.response;
      this.generalFilter = response.data.response;

      const genreArray = this.disks.map((element) => {
        return element.genre
      })
      this.musicalGenre = [...new Set(genreArray)];

    
    });

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
