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
            <span>Yu-Gi-Oh Api</span>
        </div>
    </nav>
  
</template>

<!-- --------QUI VA IL TUO CSS LEGATO A QUESTO COMPONENTS IN PARTICOLARE-------- -->
<style lang="scss">

nav{
    width: 100%;
    height: 350px;
    background-image: url('https://images5.alphacoders.com/566/566301.jpg');
    background-position: right;

    display: flex;
    align-items: center;

    .container{
        padding: 20px;
    
        span{
            font-size: 90px;
            color: blwhiteack;
            margin-left: 20px;
            font-weight: 500;
        }
    }

}

</style>
