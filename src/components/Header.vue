<template>
    <header class="text-center bg-dark">
        <h1 class="py-3 text-danger">Boolflix</h1>

        <div class="search-bar pb-3">
            <input type="text" v-model.trim="textSearch">
            <button @click="$emit('search', textSearch)" class="px-2 bg-white">Cerca </button>
        </div> 

    </header>
</template>

<script>
export default {
    name: 'Header',
    data(){
        return{
            textSearch: ''
        }
    }
}
</script>

<style>
/* .search-bar{
    
} */
</style>