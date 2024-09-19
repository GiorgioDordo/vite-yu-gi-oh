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
  }
}  
</script>

<template>
  <AppLoader v-if="cardList.length === 0"/>
  <section class="container-card container p-5" v-else>
    <div class="row">
        <AppCardItem v-for=" cardItem in cardList" :key="cardItem.id" :cardObject="cardItem" />
    </div>
  </section>
</template>

<style lang="scss" scoped>
.container-card {
  background-color: white;
}
</style>
