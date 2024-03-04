<!-- --------QUI VA I TUOI SCRIPT JS LEGATI A QUESTO COMPONENTS IN PARTICOLARE-------- -->
<script>

export default{

    name: 'AppTitle',
}

</script>

<!-- --------QUI VA IL TUO HTML LEGATO A QUESTO COMPONENTS IN PARTICOLARE-------- -->
<template>

    <nav>
        <div class="container">
            <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/11/Yu-Gi-Oh%21_%28Logo%29.jpg/640px-Yu-Gi-Oh%21_%28Logo%29.jpg" alt="logo">
            <span>Yu-Gi-Oh Api</span>
        </div>
    </nav>
  
</template>

<!-- --------QUI VA IL TUO CSS LEGATO A QUESTO COMPONENTS IN PARTICOLARE-------- -->
<style lang="scss">

nav{
    width: 100%;
    height: 100px;
    background-color: white;

    display: flex;
    align-items: center;

    .container{
        width: 1200px;
        margin: 0 auto;
        img{
            height: 30px;
        }
    
        span{
            font-size: 48px;
            color: black;
            margin-left: 20px;
            font-weight: bold;
        }
    }

}

</style>
