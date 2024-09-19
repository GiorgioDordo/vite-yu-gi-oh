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
        loaded: true,
    }
  },
}  
</script>

<template>
<AppLoader v-if="!loaded"/>
<AppCards v-else/>
</template>

<style lang="scss" scoped>

</style>
