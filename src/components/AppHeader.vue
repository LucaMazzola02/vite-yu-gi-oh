<script>

export default {
    name: 'AppHeader',
    data(){
      return {

      }
    },
}
</script>

<template>
    <header>
        <nav class="navbar bg-light">
            <div class="container">
                <a class="navbar-brand" href="#">
                <img  src="https://www.pngitem.com/pimgs/m/172-1722643_yugioh-logo-png-yu-gi-oh-logo-transparent.png" alt="Logo"  class="d-inline-block align-text-top me-4">
                    Yu-Gi_Oh API
                </a>
            </div>
        </nav>
    </header>
</template>

<style lang="scss" scoped>
header .navbar-brand{
    height: 40px;

    img{
        height: 100%;
    }

}
  

</style>