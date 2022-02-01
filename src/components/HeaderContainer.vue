<template>
    <header>
        <img src="../assets/spotify-logo.png" alt="logo">

        <div class="input-box">

            <label for="genre">GENRE</label>
            <select name="genre" id=""
            v-model="selectedGenre"
            v-on:change="$emit('genreFilter', selectedGenre)"
            >
                <option disabled value="" >Filter by Genre</option>
                <option value="">All</option>
                <option
                v-for="(item, index) in genre"
                :key="index"
                :value="item"
                >
                {{ item }}
                </option>
             </select>

            <label for="artist">ARTIST</label>
            <select name="artist" id=""
            v-model="selectedArtist"
            v-on:change="$emit('artistFilter', selectedArtist)"
            >
                    <option disabled value="" >Filter by Artist</option>
                    <option value="">All</option>
                    <option
                    v-for="(item, index) in artists"
                    :key="index"
                    :value="item"
                    >
                    {{ item }}
                    </option>
            </select>
            </div>
       

    </header>
</template>

<script>
export default {
    data() {
        return {
           selectedGenre: '',
           selectedArtist: '',


        }
    },
    props: {
        genre: Array,
        artists: Array,
    },
    methods: {
      
    }
    
}
</script>

<style lang="scss" scoped>

 header {
    height: 50px;
    background: rgb(53, 61, 71);

    display: flex;
    justify-content: space-between;
    

    img {
      height: 30px;
      margin: 10px;
      
    }
    .input-box {
        padding: 15px;
        color: white;
        

        label {
            margin-left: 20px;
            margin-right: 5px;
        }



    }


  }

</style>