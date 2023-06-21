<template>
    <main>
        <SelectedArchetype @filteredCards="getCardsFromFilter" />
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

<script>
import CardList from './CardsList.vue';
import SelectedArchetype from './SelectedArchetype.vue';
import axios from 'axios';

export default {
    name: 'AppMain',
    data(){
      return {
        apiUrl: 'https://db.ygoprodeck.com/api/v7/cardinfo.php',
        cardsList : [],

      }
    },
    components: {
        CardList,  
        SelectedArchetype,   
    },

    methods : {
        getCardsFromFilter(filter){
            axios.get(this.apiUrl, {
                params: {
                    num: 40,
                    offset: 0,
                    archetype : filter
                }
            })
                .then( (response) => {
                    // handle success
                    this.cardsList = response.data.data;
                    console.log(this.cardsList);
                })
                .catch(function (error) {
                    // handle error
                    console.log(error);
                });

        }

    },
    created(){
        this.getCardsFromFilter();
    },
}
</script>



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