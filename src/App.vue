<template>
  <div id="app">
    <Header @search="getMovie"/>
    
    <Main :moviesItem="moviesItem"/>
  </div>
</template>

<script>
import axios from 'axios';
import Header from '@/components/Header.vue';
import Main from '@/components/Main.vue';

export default{
  name: 'App',
  components:{
    Header,
    Main
  },
  data(){
    return{
      urlApi: 'https://api.themoviedb.org/3/search/movie?',
      moviesItem:[],
      textSearch:''
    }
  },
  methods:{
    getMovie(searchText){
      this.textSearch = searchText
      axios
        .get(this.urlApi, {
          params:{
            api_key: 'c81548416aaaa14e591c85d4db9fdc1e',
            language: 'it-IT',
            query: this.textSearch
          }
        })
        .then(response => {
          console.log(response.data.results);
          this.moviesItem = response.data.results          
        })
        .catch(error =>{
          console.log('Errore ', error);
        })
    }
  }
}
</script>

<style lang="scss">
@import '@/style/commons.scss';
</style>