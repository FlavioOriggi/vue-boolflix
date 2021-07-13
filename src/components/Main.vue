<template>
    <main> 
        <div class="container-xl">  
            <div class="row pt-2"> 
                <div class="col">   
                    <div class="cards-contenent pt-2">
                        <h3>Films</h3>
                        <CardMovie v-for="(item, index) in moviesItem" :key="index" :movie="item"/>
                    </div>

                    <div class="cards-contenent pt-2">
                        <h3>Serie TV</h3>
                        <CardSTv v-for="(item, index) in serietvItem" :key="index" :SerieTV="item"/>
                    </div>
                </div>
            </div> 
        </div>
    </main>
</template>

<script>
import CardMovie from "@/components/CardMovie";
import CardSTv from "@/components/CardSTv";


export default {
    name: 'Main',
    props: {
        moviesItem : Array,
        serietvItem : Array
    },
    components: {
        CardMovie,
        CardSTv        
    }
}
</script>

<style>
</style>