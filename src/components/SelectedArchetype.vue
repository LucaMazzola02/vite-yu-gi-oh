<script>
import axios from 'axios';

export default {
    name: 'SelectedArchetype',
    data(){
      return {
        selectedFilter : '',
        cardsArchetypes : [],

      }
    },
    methods: {
        getArchetypes(){
            axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
                .then( (response) => {
                    // handle success
                    this.cardsArchetypes = response.data;
                    console.log(this.cardsArchetypes);
                })
                .catch(function (error) {
                    // handle error
                    console.log(error);
                });
        },
    },

    created(){
        this.getArchetypes();
    }
}
</script>

<template>
    <div class="container">
        <div class="row py-4">
            <label for="cards-select"></label>
            <select class="selected" name="cards-select" id="cards-select" v-model="selectedFilter"
                @change="$emit('filteredCards', selectedFilter)">
                <option v-for="cardArchetype in cardsArchetypes" :value="cardArchetype.archetype_name" >
                {{ cardArchetype.archetype_name }}
                </option>
            </select>
        </div>
    </div>
    
</template>

<style lang="scss" scoped>
.selected{
    width: 270px;

}


</style>