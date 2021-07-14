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
                        <CardTv v-for="(item, index) in serietvItem" :key="index" :tv="item"/>
                    </div>
                </div>
            </div> 
        </div>
    </main>
</template>

<script>
import CardMovie from "@/components/CardMovie";
import CardTv from "@/components/CardTv";


export default {
    name: 'Main',
    props: [ "moviesItem", "serietvItem", "textSearch"],
    components: {
        CardMovie,
        CardTv        
    }
}
</script>

<style>
</style>