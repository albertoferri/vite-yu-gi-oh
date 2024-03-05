<script>
// importiamo lo store
import {store} from '../store.js';

export default {
    data(){
        return{
            store,
        }
    }

}

</script>

<template>
    <div class="container">

        <div id="search-bar">
            <select name="search" id="arch-select" @change="$emit('search')">
                <option v-for="archetype in this.store.archetypes" :value="archetype.archetype_name">
                    {{ archetype.archetype_name }}
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
            width: 120px;
            padding: 6px 8px;
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