<script>

export default {
    name: 'SelectedArchetype',
    data(){
      return {
        searchedText : '',

      }
    }
}
</script>

<template>
    <div class="container">
        <div class="row py-4">
            <input type="text" class="form-control" placeholder="Character name" aria-label="Character name" aria-describedby="basic-addon1"  v-model="searchedText"

                @keyup.enter="$emit('searched', searchedText)">
        </div>
    </div>
    
</template>

<style lang="scss" scoped>
.selected{
    width: 270px;

}


</style>