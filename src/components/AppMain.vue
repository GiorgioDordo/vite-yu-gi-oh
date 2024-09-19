<script>
import AppLoader from './AppLoader.vue';
import AppCards from './AppCards.vue';

export default {
    components: {
        AppLoader,
        AppCards
    },
  data () {
    return {
        loaded: false,
    }
  },
}  
</script>

<template>
<h1>MAIN</h1>
<AppLoader v-if="!loaded"/>
<AppCards v-else/>
</template>

<style lang="scss" scoped>

</style>
