<template>
    <main>        
        <div class="cards-contenent pt-2">
            <h3>Films</h3>
            <CardMovie v-for="(item, index) in moviesItem" :key="index" :movie="item"/>
        </div>
    </main>
</template>

<script>
import CardMovie from "@/components/CardMovie";

export default {
    name: 'Main',
    props: {
        moviesItem : Array
    },
    components: {
        CardMovie        
    }
}
</script>

<style>
</style>