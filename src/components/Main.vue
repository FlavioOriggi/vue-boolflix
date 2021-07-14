<template>
    <main> 
        <div class="container-xl">  
            <div class="row pt-2">
                               
                <div v-if="films.length != 0" class="col"> 
                    <h3>Films</h3>                     
                    <div class="cards-contenent d-flex  pt-2">
                        <Card v-for="film in films" :key="film.id" :info="film"/>
                    </div>
                    
                </div>
            </div>

            <div class="row pt-2">                    
                <div v-if="tv.length != 0"  class="col">
                    <h3>Serie TV</h3>
                    <div class="cards-contenent pt-2 d-flex">
                        <Card v-for="serietv in tv" :key="serietv.id" :info="serietv"/>
                    </div>
                </div>                    
            </div> 
        </div>
    </main>
</template>

<script>
// import CardMovie from "@/components/CardMovie";
// import CardTv from "@/components/CardTv";
import Card from "@/components/Card";


export default {
    name: 'Main',
    props: [ "films", "tv", "textSearch"],
    components: {
        Card    
        // CardMovie,
        // CardTv  
          
    }
}
</script>

<style scoped lang="scss">>
main{
    height: calc(100vh - 88px); 
}
    
    


</style>