<script>

export default {
  data () {
    return {
    }
  },
}  
</script>

<template>
<div class="card-wrapper">
    <div class="card-wrapper">
    <img class="card" src="/src/assets/img/" alt="" />
    <img class="card card-back" src="back.jpg" alt="" />
</div>

</div>

</template>

<style lang="scss" scoped>
@keyframes cardFlip {
  0% {
    transform: rotateY(0deg);
  }
  50% {
    transform: rotateY(180deg);
  }
  100% {
    transform: rotateY(0deg);
  }
}

.card-wrapper {
  position: relative;
  transform-style: preserve-3d;
  animation: cardFlip 3s ease-in-out infinite;
  width: 100px;
  height: 150px;
}

.card {
  position: absolute;
  backface-visibility: hidden;
  width: 100px;
  height: 150px;
}

.card-back {
  transform: rotateY(180deg);
}


</style>
