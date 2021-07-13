<template>
  <div id="app">
    <Header @search="getMovie"/>
    
    <Main :moviesItem="moviesItem" :serietvItem="serietvItem" />    

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
      moviesApi: 'https://api.themoviedb.org/3/search/movie?',
      seriesApi : 'https://api.themoviedb.org/3/search/tv?',
      moviesItem:'',
      textSearch:'',
      serietvItem:''
    }
  },
  methods:{
    getMovie(searchText){

      this.textSearch = searchText;
      
      axios
        .get(this.moviesApi, {
          params:{
            api_key: 'd91be32ec828fa4f2c317ac78d3e0690',
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
    },

    getSeries(searchText){
      this.textSearch = searchText;
      
      axios
        .get(this.seriesApi, {
          params:{
            api_key: 'd91be32ec828fa4f2c317ac78d3e0690',
            language: 'it-IT',
            query: this.textSearch
          }
        })
        .then(find => {
          console.log(find.data.results);
          this.serietvItem = find.data.results          
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