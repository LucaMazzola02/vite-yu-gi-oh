<script>

export default {
    name: 'SelectedArchetype',
    data(){
      return {

      }
    },
}
</script>

<template>
    <div class="container">
        <div class="row py-4">
            <select class=" selected form-select " aria-label="Default select example">
                <option selected>Open this select menu</option>
                <option value="1">One</option>
                <option value="2">Two</option>
                <option value="3">Three</option>
            </select>
        </div>
    </div>
    
</template>

<style lang="scss" scoped>
.selected{
    width: 270px;

}


</style>