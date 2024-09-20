<script>
export default {
  data () {
    return {
    }
  },
  props: {
    cardObject: {
      type: Object,
      required: true,
    }
  }
}
</script>

<template>
<div class="col-6 col-lg-3">
    <article class="card w-100">
        <img :src=" cardObject.card_images[0].image_url " class="card-img-top" alt="...">
        <div class="card-body">
            <p class="card-text"><strong>Archetype:</strong>{{ cardObject.archetype }}</p>
            <p class="card-text"><strong>Name:</strong>{{ cardObject.name }}</p>
            <p class="card-text"><strong>Race:</strong>{{ cardObject.race }}</p>
            <p class="card-text"><strong>Type:</strong>{{ cardObject.type }}</p>
        </div>
    </article>
</div>
</template>

<style lang="scss" scoped>

</style>
