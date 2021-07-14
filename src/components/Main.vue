<template>
    <main> 
        <div class="container-xl">  
            <div class="row pt-2"> 
                <div class="col">   
                    <div class="cards-contenent pt-2">
                        <h3>Films</h3>
                        <Card v-for="film in movie" :key="film.id" :info="film"/>
                    </div>

                    <div class="cards-contenent pt-2">
                        <h3>Serie TV</h3>
                        <Card v-for="serietv in tv" :key="serietv.id" :info="item"/>
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

<style>
</style>