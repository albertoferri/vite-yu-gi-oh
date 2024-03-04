<!-- --------QUI VA I TUOI SCRIPT JS LEGATI A QUESTO COMPONENTS IN PARTICOLARE-------- -->
<script>
import AppCard from "./AppCard.vue";
import AppPagination from "./AppPagination.vue";

import {store} from '../store.js';


export default{

    name: 'AppCardContainer',

    components:{
        AppCard,
        AppPagination,
    },
    data(){
        return{
            store,
        }
    }
}

</script>

<!-- --------QUI VA IL TUO HTML LEGATO A QUESTO COMPONENTS IN PARTICOLARE-------- -->
<template>
    
    <main>
        <div class="container">
            <AppPagination></AppPagination>
    
            <ul>
                <AppCard 
                    v-for="(card, index) in store.cards"
                    :key="index"
                    :card="card"
                ></AppCard>
               
            </ul>
        </div>

    </main>
</template>

<!-- --------QUI VA IL TUO CSS LEGATO A QUESTO COMPONENTS IN PARTICOLARE-------- -->
<style scoped lang="scss">

main{
    background-color: #d48f38;
    padding: 20px;

    .container{
        width: 1200px;
        margin: 0 auto;
        background-color: white;

        ul{
            list-style-type: none;

            display: flex;
            justify-content: space-between;
            flex-flow: row wrap;
            gap: 24px;

            padding: 20px;

            
        }
    }
}

</style>
