<template>
    <div class="card">        
        <div>
            <img v-if="SerieTV.poster_path" :src="'https://image.tmdb.org/t/p/w342/' + SerieTV.poster_path" >
            
        </div>
        <div><span class="fw-bold">Titolo:</span> {{SerieTV.title}}</div>
        <div><span class="fw-bold">Titolo originale:</span> {{SerieTV.original_title}}</div>
        <div class="fw-bold d-flex">
            
            <div class="me-2">Lingua: </div>
            <div>
                <img class="flag" v-if="flagArr.includes(SerieTV.original_language)" :src="require('../assets/'+SerieTV.original_language+'.png')" :alt="SerieTV.original_language">
                <span v-else>{{SerieTV.original_language}}</span>
            </div>
            
        </div>
        <div><span class="fw-bold">Voto:</span> {{ starsVote }} </div>            
    </div>
</template>

<script>
export default {
    name: 'CardSTv',
    props: ['SerieTV'],
    data(){
        return{
            flagArr: ['en','es','it', 'us'],
            getImage: '',
            starsVote: ''
        }
    },
    methods: {
        voteImage(){
            this.starsVote = Math.round(this.vote / 2);          
            return this.starsVote
        }
    },
}
</script>

<style>  

.flag{
    width: 15px;
}
</style>