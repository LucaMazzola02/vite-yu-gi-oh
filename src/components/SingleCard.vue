<script>


export default {
    name:'SingleCard',
    data(){
        return {

        }
    },
    props:{
        name : String,
        type : String,
        image : String,
    }
}
</script>

<template>
    <article v-for="cardImage in image" class="card mb-5 col-2 me-1 p-0">
        <img :src="cardImage.image_url" class="w-100" :alt="name + ' image'">
        <div class="card-body text-center">
            <h5 class="card-title fw-bold">
                {{ name }}
            </h5>
            <p class="card-text">
                {{ type }} 
            </p>    
        </div>
    </article>
    
</template>

<style lang="scss">

    article{
        box-shadow: rgba(0, 0, 0, 0.25) 0px 54px 55px, rgba(0, 0, 0, 0.12) 0px -12px 30px, rgba(0, 0, 0, 0.12) 0px 4px 6px, rgba(0, 0, 0, 0.17) 0px 12px 13px, rgba(0, 0, 0, 0.09) 0px -3px 5px;
    }
    .card:hover{
        transform: scale(1.1);
    }

    .card-body{
        background-color: rgba(212,143,56,255);

        .card-title,{
            color: #fff;
    }}

</style>