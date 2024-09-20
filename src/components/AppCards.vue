<script>
import AppCardItem from './AppCardItem.vue';
import AppLoader from './AppLoader.vue';
import axios from 'axios';

export default {
  data () {
    return {
            cardList: [],
            apiUrl: 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0',
            loaded: false,
    }
  },
  methods: {

    getCards() {

setTimeout(() => {

      axios.get(this.apiUrl)
        .then((response) => {
          console.log(response.data.data);
          this.cardList = response.data.data;
        })
        .catch(function (error) {
          console.log(error);
        });

      },5000);

    }
  },

  components: {
    AppCardItem,
    AppLoader
  },

  created() {
    this.getCards();
  },
}  
</script>

<template>
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
