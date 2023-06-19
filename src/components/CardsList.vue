<script>
import SingleCard from './SingleCard.vue';
import axios from 'axios';
export default {
    name:'CardsList',
    data(){
        return {
            apiUrl: 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0',
            cardsList : [],
        }
    },
    components:{
        SingleCard,
    },

    created(){
        axios.get(this.apiUrl)
        .then( (response) => {
            console.log(response.data.data);
            this.cardsList = response.data.data;
        })
        .catch(function (error) {
            console.log(error);
        })
    }
}
</script>

<template>
        <div class="row py-3 justify-content-between">
            <SingleCard v-for="character in cardsList"
                :name="character.name"
                :type="character.archetype"
                :image="character.card_images"
            />
        </div>
</template>

<style lang="scss">

</style>