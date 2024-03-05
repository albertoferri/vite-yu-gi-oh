<script>
// per importare axios (dopo essere stato installato) 
import axios from 'axios';
// importiamo lo store
import {store} from './store.js';


import AppTitle from './components/AppTitle.vue';
import AppCardContainer from './components/AppCardContainer.vue';
// import AppLoader from './components/AppLoader.vue';
import AppSearch from './components/AppSearch.vue';

export default{

  data(){
    return{

      // dichiariamo lo store, utilizzabile nel nostro componente
      store,
    }
  },
  created() {
    // spazio di codice che viene eseguito appena l'applicazione viene lanciata
    
    // creo una funzione axios get per estrapolare la proprietà che mi serve da questo api:https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=40&offset=80')
      .then(response => {
        this.store.cards = response.data.data;
        // console.log("Array in lista:", response.data.data);

      })

  },



  components:{
    AppTitle,
    AppCardContainer,
    AppSearch,
  },

  methods: {

  searchArchetype() {

    axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
    .then(response => {
      console.log(response.data);
      this.store.archetypes = response.data.map(item => item.archetype_name);
      this.$forceUpdate();
      // console.log(this.store.archetypes);
    })


    console.log("Ricerca percepita")
  },

},

  





}
</script>

<template>
  <!-- <AppLoader v-if="! store.cards.length > 0"></AppLoader> -->

  
  <AppTitle></AppTitle>
  <AppSearch @change="searchArchetype()"></AppSearch>
  <AppCardContainer></AppCardContainer>
  
</template>

<style lang="scss">


</style>
