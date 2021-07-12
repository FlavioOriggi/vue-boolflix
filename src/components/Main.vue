<template>
  <main>
      <div v-for="(movie, item) in moviesItem" :key="item" class="card-contenent">
          <div class="card">
              <p>Titolo: {{movie.title}}</p>
              <p>Titolo originale: {{movie.original_title}}</p>
              <p>Lingua: {{movie.original_language}}</p>
              <p>Voto: {{movie.vote_average}}</p>
          </div>          
      </div>
  </main>
</template>

<script>
export default {
    name: 'Main',
    props:['moviesItem']
}
</script>

<style>    

</style>