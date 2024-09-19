<script setup>
import AppHeader from './components/AppHeader.vue'
import AppMain from './components/AppMain.vue'

export default {
  data () {
    return {
    }
  },
  components: [
    AppHeader,
    AppMain
  ]
}
</script>

<template>
<AppHeader />
<AppMain />
</template>

<style lang="scss" scoped>
@use '../node_modules/bootstrap/scss/bootstrap.scss'
@use './general.scss'
</style>
