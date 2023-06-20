<script>
import CardList from './CardsList.vue';
import SelectedArchetype from './SelectedArchetype.vue';
import axios from 'axios';

export default {
    name: 'AppMain',
    data(){
      return {
        apiUrl: 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=39&offset=0',
        cardsList : [],

      }
    },
    components: {
        CardList,  
        SelectedArchetype,   
    },
    created(){
        axios.get(this.apiUrl)
              .then( (response) => {
                    this.cardsList = response.data.data;
                })
                .catch(function (error) {
                    console.log(error);
                })
    }
}
</script>

<template>
    <main>
        <SelectedArchetype />
        <div class="container bg-light p-5">
            <div class="row title mb-3">
                    <h2>Found 39 cards</h2>
            </div>
            <CardList 
              :cardsList="cardsList" 
              />
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