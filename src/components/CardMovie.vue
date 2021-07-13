<template>

    <div class="card">
        <div><span class="fw-bold">Titolo:</span> {{movie.title}}</div>
        <div><span class="fw-bold">Titolo originale:</span> {{movie.original_title}}</div>
        <div class="fw-bold">
            
            <span>Lingua: </span>
            <div>
                <img v-if="flagArr.includes(movie.original_language)" :src="require('../assets/'+movie.original_language+'.png')" :alt="movie.original_language">
                <span v-else>{{movie.original_language}}</span>
            </div>
            
        </div>
        <div><span class="fw-bold">Voto:</span> {{movie.vote_average}}</div>            
    </div>
</template>

<script>
export default {
    name: 'CardMovie',
    props: ['movie'],
    data(){
        return{
            flagArr: ['en','es','it', 'us']
        }
    }
}
</script>

<style>      
</style>

    
