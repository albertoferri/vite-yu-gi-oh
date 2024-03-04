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
        <p>Found {{ store.cards.length }} cards</p>
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