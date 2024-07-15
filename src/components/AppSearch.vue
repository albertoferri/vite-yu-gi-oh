<script>

import AppPagination from './AppPagination.vue';


// importiamo lo store
import {store} from '../store.js';

export default {

    
    data(){
        return{
            store,
        }
    },

    component: {
        AppPagination,
    }

}

</script>

<template>
    <div class="container">
        <div>
            <a href="/" class="button">HOME</a>
        </div>

        <div id="search-bar">
            FILTRA PER TIPOLOGIA:

            <select 
                name="search" 
                id="arch-select" 
                @change="$emit('filter')"
                v-model="store.filterValue"
            >
                <option v-for="currentArchetype in store.archetypes" :value="currentArchetype.archetype_name">
                    {{ currentArchetype.archetype_name }}
                </option>
            </select>

        </div>
        
    </div>

</template>

<style lang="scss" scoped>
.container {
    padding: 20px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    

    #search-bar {
        display: flex;
        align-items: center;
        gap: 12px;
        
        
        #arch-select {
            width: 250px;
            padding: 8px 10px;
            text-align: center;
            text-transform: uppercase;
        }
    }

    .button {
        border: 1px solid white;
        border-radius: 4px;
        padding: 8px 12px;
        text-transform: uppercase;
        text-decoration: none;
        color: white;
        font-weight: bold;


        &:hover{
            background-color: white;
            color: black;
        }
    }
}

</style>