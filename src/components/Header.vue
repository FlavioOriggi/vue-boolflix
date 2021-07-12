<template>
    <header class="text-center">
        <h1 class="py-3">boolflix</h1>

        <div class="search-bar">
            <input type="text" v-model.trim="textSearch">
            <button @click="$emit('search', textSearch)" class="px-2">Cerca </button>
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