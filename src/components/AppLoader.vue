<script>

export default {
  data () {
    return {
    }
  },
}  
</script>

<template>
<!-- This card loader was taken from: https://christopherkade.com/posts/css-card-flip -->
<div class="card-wrapper d-flex justify-content-center">
    <img class="card" src="/src/assets/img/front.jpg" alt="" />
    <img class="card card-back" src="/src/assets/img/back.jpg" alt="" />
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
  width: 170px;
  height: 255px;

  position: absolute;
  top: 50%;
  left: 44%;
  transform: translate(-50%, -50%);
}

.card {
  position: absolute;
  backface-visibility: hidden;
  width: 170px;
  height: 255px;
}

.card-back {
  transform: rotateY(180deg);
}


</style>
