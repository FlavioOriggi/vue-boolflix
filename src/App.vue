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
      urlApi: 'https://api.themoviedb.org/3/search/',
      moviesItem:'',
      textSearch:'',
      serietvItem:''
    }
  },
  methods:{
    getMovie(searchText){

      this.textSearch = searchText;
      
      axios
        .get(this.urlApi+'movie', {
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
        }),
      
      axios
        .get(this.urlApi+'tv', {
          params:{
            api_key: 'd91be32ec828fa4f2c317ac78d3e0690',
            language: 'it-IT',
            query: this.textSearch
          }
        })
        .then(response => {
          console.log(response.data.results);
          this.serietvItem = response.data.results          
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