<template>
    <header class="bg-dark">
        <div class="container-xl">
            <div class="row d-flex">
                <div class="col-6">
                    <h1 class="py-3 text-danger">Boolflix</h1>
                </div>
                <div class="col-6  align-self-center">
                    <div class="search-bar d-flex justify-content-end">
                        <input type="text" v-model.trim="textSearch" placeholder="Cerca un titolo" class=" text-white bg-dark border-light">
                        <button @click="$emit('search', textSearch)" class="text-white bg-dark px-2 border-light">Cerca </button>
                    </div> 
                </div>
            </div> 
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

<style scoped lang="scss">
/* .search-bar{
    
} */
</style>