<script>
import AppCardItem from './AppCardItem.vue';
import AppLoader from './AppLoader.vue';
import AppSearchCard from './AppSearchCard.vue';
import axios from 'axios';

export default {
  data () {
    return {
            cardList: [],
            apiUrl: 'https://db.ygoprodeck.com/api/v7/cardinfo.php',
    }
  },
  methods: {

    getCards( archetype = "" ) {
      axios.get(this.apiUrl, {
        params: {
          // num: 36,
          // offset: 0,
          archetype: archetype
        }
      })
        .then((response) => {
          console.log(response.data.data);
          this.cardList = response.data.data;
        })
        .catch(function (error) {
          console.log(error);
        })
        .finally(() => {
          this.loading = false;
          console.log("Chiamata API terminata")
        });
    },

    searchCardArchetype(searchedInput) {
    console.log(searchedInput);
    this.getCards(searchedInput);
    }

  },

  components: {
    AppCardItem,
    AppLoader,
    AppSearchCard
  },

  created() {
    this.getCards();
  },

  created() {
    setTimeout(this.getCards, 1000);
  }
}  
</script>

<template>
      <AppSearchCard @search-card="searchCardArchetype" />
  <div class="container">
  <AppLoader v-if="cardList.length === 0" class="m-auto"/>
  <section class="container-card p-5 d-flex flex-column" v-else>
    <h1 class="align-self-center mb-5"><strong>Cards:</strong>{{cardList.length}}</h1>
    <div class="row">
        <AppCardItem v-for=" cardItem in cardList" :key="cardItem.id" :cardObject="cardItem" class="mb-4" />
    </div>
  </section>
  </div>
</template>

<style lang="scss" scoped>
.container-card {
  background-color: white;
}
</style>
