<script>
import AppCardItem from './AppCardItem.vue';

export default {
  data () {
    return {
    }
  },
  components: {
    AppCardItem
  }
}  
</script>

<template>
  <section class="container-card container p-5">
    <div class="row">
      <div class="col-6 col-lg-3" v-for="n in 10">
        <AppCardItem />
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.container-card {
  background-color: white;
}
</style>
