<template>
  <main>
    <MyFilters @filter="selectNewGenre"/>
    <div id="content-container">
      <AlbumCard
      v-for="(album, i) in genreFilter" :key="i" 
      :img="album.poster" 
      :text="album.author" 
      :date="album.year"
      :albumName="album.title"
      />
    </div>
  </main>
</template>

<script>
import axios from 'axios'
import AlbumCard from './AlbumCard.vue'
import MyFilters from './MyFilters.vue';

export default {
    name: "MyContent",
    data() {
        return {
            apiSpotify: "https://flynn.boolean.careers/exercises/api/array/music",
            albumList: [],
            choseGenre : ''
        };
    },
    methods : {
      selectNewGenre (checkGenre) {
        this.choseGenre = checkGenre;
        
      }
    },
    computed : {
      genreFilter () {      
        if (this.choseGenre === 'all') {
          console.log(this.choseGenre);
          return this.albumList
        } else {
            return this.albumList.filter(item => {
              console.log(this.choseGenre);
                return item.genre.toLowerCase().includes(this.choseGenre.toLowerCase())
          });
        }
      }
    },
    created() {
        axios.get(this.apiSpotify)
            .then((result) => {
            this.albumList = result.data.response;
            this.albumList[0].poster = 'https://www.vinileria.it/wp-content/uploads/2022/04/R-865216-1338266621-3764.jpg';
            // console.log(this.albumList);
        })
            .catch((error) => {
            console.log("errore", error);
        });
    },
    components: {
       AlbumCard,
        MyFilters
    }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

  main {
    min-height: calc(100vh);
    width: 100%;
    background-color: #1e2d3b;
    padding: 50px 250px;

    #content-container {
      width: 100%;
      height: 100%;
      display: flex;
      flex-wrap: wrap;
      margin-top: 50px;
    }
  }

  @import '../assets/style/MyContentMedias.scss'

</style>
