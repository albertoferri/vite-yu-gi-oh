<!-- --------QUI VA I TUOI SCRIPT JS LEGATI A QUESTO COMPONENTS IN PARTICOLARE-------- -->
<script>

export default{

    name: 'AppCard',
    props:{
        card: Object
    },
}

// console.dir(card)
</script>

<!-- --------QUI VA IL TUO HTML LEGATO A QUESTO COMPONENTS IN PARTICOLARE-------- -->
<template>

<li class="card">
    <img :src="card.card_images[0].image_url_small" :alt="card.name">
    <h3>{{ card.name }}</h3>
    <span>{{ card.archetype }}</span>
</li>


  
</template>

<!-- --------QUI VA IL TUO CSS LEGATO A QUESTO COMPONENTS IN PARTICOLARE-------- -->
<style scoped lang="scss">

.card{
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: .7em;

    width: calc(100% / 5 - 24px);

    background-color: #d48f38;

    img{
        width: 100%;
    }

    h3{
        text-align: center;
        font-weight: bold;
    }

    span{
        color: black;
    }
}


</style>
