<script>
import AppCards from './AppCards.vue';
import AppSearchCard from './AppSearchCard.vue';

export default {
    components: {
        AppCards,
        AppSearchCard
    },
  data () {
    return {
    }
  },

  searchCardArchetype() {
    console.log("");
  }
}  
</script>

<template>
  <AppSearchCard @search-card="" />
  <AppCards />
</template>

<style lang="scss" scoped>

</style>
