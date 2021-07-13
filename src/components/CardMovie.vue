<template>
    <div class="card p-2">
        
        <div><span class="fw-bold">Titolo:</span> {{movie.title}}</div>
        <div><span class="fw-bold">Titolo originale:</span> {{movie.original_title}}</div>
        <div class="my-1">
            <img :src="'https://image.tmdb.org/t/p/w342/' + movie.poster_path" >
            
        </div>
        <div class="fw-bold d-flex">
            
            <div class="me-2">Lingua: </div>
            <div>
                <img class="flag" v-if="flagArr.includes(movie.original_language)" :src="require('../assets/'+movie.original_language+'.png')" :alt="movie.original_language">
                <span v-else>{{movie.original_language}}</span>
            </div>
            
        </div>
        <div><span class="fw-bold">Voto:</span> {{ starsVote }}</div>            
    </div>
</template>

<script>
export default {
    name: 'CardMovie',
    props: ['movie'],
    data(){
        return{
            flagArr: ['en','es','it', 'us'],            
            starsVote: ''
        }
    },
    methods: {
        getVote(){
            this.starsVote = Math.round(this.vote / 2);            
            return this.starsVote
        }       
    },
}
</script>

<style> 
img{
    width: 10%;
} 

.flag{
    width: 15px;
}
</style>

    
