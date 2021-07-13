<template>
    <main>        
        <div class="cards-contenent">
            <h3>Films</h3>
            <Card v-for="(item, index) in moviesItem" :key="index" :movie="item"/>
        </div>
    </main>
</template>

<script>
import CardMovie from "@/components/CardMovie";

export default {
    name: 'Main',
    components: {
        CardMovie,
        // CardSeriesTv
    }
}
</script>

<style>
</style>