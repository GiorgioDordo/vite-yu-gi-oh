<script>
export default {
  data () {
    return {
        searchedString:"",
    }
  },
  methods: {
    searchCards(message){
        console.log(message);
        this.$emit("searchCard", message)
    }
  }
  
}
</script>

<template>
<div class="container d-flex justify-content-center mb-5">
    <input type="text" placeholder="Search Archetype"  @keyup.enter="searchCards(searchedString)" v-model="searchedString">
</div>
</template>

<style lang="scss" scoped>

</style>
