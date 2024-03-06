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
        Numero di carte: {{ store.numberOfCards }}
    </div>
</section>

</template>

<style lang="scss">
@use '../styles/variables' as *;

section {
    color: white;

    padding: 20px;

    background-color: $bg-dark;

    
}

</style>