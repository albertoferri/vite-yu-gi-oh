<script>
import {store} from '../store.js';

export default {
    name: 'AppPagination',


    data() {
        return {
            store,
        }
    }

}

</script>

<template>

<section>
    <div class="container">
        Elementi in pagina: {{ store.cards.length }}
    </div>
</section>

</template>

<style lang="scss">

section {
    color: white;

    padding: 20px;

    background-color: #212529;

    
}

</style>