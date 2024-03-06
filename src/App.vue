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

  components:{
    AppTitle,
    AppCardContainer,
    AppSearch,
  },


  created() {
    // spazio di codice che viene eseguito appena l'applicazione viene lanciata
    
    // creo una funzione axios get per estrapolare la proprietà che mi serve da questo api:https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=40&offset=80')
      .then(response => {
        this.store.cards = response.data.data;
        // console.log("Array in lista:", response.data.data);

      });

      // chiamata api per popolare la select archetypes

      axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
      .then(res=> {
        console.log('archetipi', res.data)
        this.store.archetypes = res.data
      })

  },


  methods: {

    filterCards() {
      // console.log('Richiesta di filtro')
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0&archetype=' + this.store.filterValue) 
        .then(res => {
          console.log('Numero di carte', res.data.meta.total_rows);
          this.store.numberOfCards = res.data.meta.total_rows;
          this.store.cards = res.data.data;
      });
    },

},


}
</script>

<template>

  
  <AppTitle></AppTitle>
  <AppSearch @filter="filterCards"></AppSearch>
  <AppCardContainer></AppCardContainer>
  
</template>

<style lang="scss">


</style>
