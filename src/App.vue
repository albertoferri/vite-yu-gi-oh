<script>
// per importare axios (dopo essere stato installato) 
import axios from 'axios';
// importiamo lo store
import {store} from './store.js';


import AppTitle from './components/AppTitle.vue';
import AppCardContainer from './components/AppCardContainer.vue';

export default{

  data(){
    return{
      cards: [],

      // dichiariamo lo store, utilizzabile nel nostro componente
      store,
    }
  },
  created() {
    // spazio di codice che viene eseguito appena l'applicazione viene lanciata
    
    // creo una funzione axios get per estrapolare la proprietà che mi serve da questo api:https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
      .then(response => {
        console.log(response.data.data[0].card_images[0].image_url);
        console.log(response.data.data);
        this.store.cards = response.data.data;

      })

  },



  components:{
    AppTitle,
    AppCardContainer,
  }
}
</script>

<template>

  <AppTitle></AppTitle>
  <AppCardContainer></AppCardContainer>
  
</template>

<style lang="scss">


</style>
