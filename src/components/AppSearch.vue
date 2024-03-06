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

        <div id="search-bar">
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
    

    #search-bar {
        display: flex;
        gap: 12px;
        
        
        #arch-select {
            width: 250px;
            padding: 8px 10px;
            text-align: center;
            text-transform: uppercase;
        }
        
        button {
            padding: 8px 12px;
            text-transform: uppercase
        }
    }
}

</style>