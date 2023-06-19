<script>
import CardList from './CardsList.vue';

export default {
    name: 'AppMain',
    data(){
      return {

      }
    },
    components: {
        CardList,  
    }
}
</script>

<template>
    <main>
        .
        <div class="container bg-light p-5">
            <div class="row title mb-3">
                    <h2>Found 39 cards</h2>
            </div>
            <CardList />
        </div>
        
    </main> 
</template>

<style lang="scss" scoped>

main{
    background-color: rgba(212,143,56,255);
}

.title{
    background-color: rgba(33,37,41,255);

    & h2{
        color: #fff;
        padding: 2rem 1rem;
    }
}

</style>