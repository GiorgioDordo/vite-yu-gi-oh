<script>
import AppCardItem from './AppCardItem.vue';
import axios from 'axios';

export default {
  data () {
    return {
            cardList: [],
            apiUrl: 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0'
    }
  },
  methods: {

    getCards() {

      axios.get(this.apiUrl)
        .then((response) => {
          console.log(response.data.data);
          this.cardList = response.data.data;
        })
        .catch(function (error) {
          console.log(error);
        });
    }
  },

  components: {
    AppCardItem
  },

  created() {
    this.getCards();
  }
}  
</script>

<template>
  <section class="container-card container p-5">
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
