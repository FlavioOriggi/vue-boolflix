<template>
    <div class="card">        
        <div>
            <img v-if="tv.poster_path" :src="'https://image.tmdb.org/t/p/w342/' + tv.poster_path" >
            
        </div>
        <div><span class="fw-bold">Titolo:</span> {{tv.title}}</div>
        <div><span class="fw-bold">Titolo originale:</span> {{tv.original_title}}</div>
        <div class="fw-bold d-flex">
            
            <div class="me-2">Lingua: </div>
            <div>
                <img class="flag" v-if="flagArr.includes(tv.original_language)" :src="require('../assets/'+tv.original_language+'.png')" :alt="tv.original_language">
                <span v-else>{{tv.original_language}}</span>
            </div>
            
        </div>
        <div><span class="fw-bold">Voto:</span> {{ starsVote }} </div>            
    </div>
</template>

<script>
export default {
    name: 'CardTv',
    props: ['tv'],
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