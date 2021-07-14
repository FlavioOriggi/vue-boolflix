<template>
     
        <div class="row">
            <div class="col">
                <div class="card p-2">       
                    
                    <img class="img-card" v-if="info.poster_path" :src="'https://image.tmdb.org/t/p/w342/' + info.poster_path " >
                    <img class="img-card" v-else :src="require('../assets/haventImg.png')" alt="not-found" >
                
                    <div class="card-contenent">
                        <div><span class="fw-bold">Titolo:</span> {{ info.title == null ? info.name : info.title}}</div>
                        <div><span class="fw-bold">Titolo originale:</span> {{info.original_title || info.original_name }}</div>
                        <div class=" d-flex">
                            
                            <div class="me-2 fw-bold">Lingua: </div>
                            <div>
                                <img class="flag" v-if="flagArr.includes(info.original_language)" :src="require('../assets/'+info.original_language+'.png')" :alt="info.original_language">
                                <span v-else>{{info.original_language}}</span>
                            </div>
                            
                        </div>
                        <div><span class="fw-bold">Vote: </span> <i v-for="(star,index) in stars(info.vote_average)" :key="index"  class="fas fa-star"></i> </div> 
                    </div>           
                </div>
            </div>
        </div>
    
</template>

<script>
export default {
    name: 'Card',
    props: ['info'],
    data(){
        return{
            flagArr: ['en','es','it', 'us'],
            starsVote: ''
        }
    },
    methods: {
        stars(vote){
            return parseInt(Math.round(vote / 2))
        }  
    }
}
</script>

<style >
.img-card{
    width: 150px;
    position: relative
}

.card:hover{    
    background-color: rgb(255, 255, 255);
    display: block;
    cursor: pointer;
                                   
}

.card-contenent{
    position: absolute;
    /* display: none; */
}

.flag{
    width: 15px;
}

</style>