<script>
import AppCardItem from './AppCardItem.vue';

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
          console.log(response);
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
        <AppCardItem />
    </div>
  </section>
</template>

<style lang="scss" scoped>
.container-card {
  background-color: white;
}
</style>
