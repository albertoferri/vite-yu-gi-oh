<script>

export default {
    data(){
        return{
            type: [],
        }
    }

}

</script>

<template>
    <div class="container">

        <div id="search-bar">
            <select name="search" id="arch-select" @click="$emit('search')">
                <option value="">alien</option>
                <option value="">alien</option>
                <option value="">alien</option>
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
        
        margin-bottom: 1em;
        
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