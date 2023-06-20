<script>
import SingleCard from './SingleCard.vue';

export default {
    name:'CardsList',
    data(){
        return {
            
        }
    },
    components:{
        SingleCard,
    },
    props:{
        cardsList : Array,
    },
    
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