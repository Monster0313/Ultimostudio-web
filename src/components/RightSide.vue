<template>
  <div id="rightSide">
    <div class="rightSide-wrap">
      <div class="rightSide-content">
        <img src="../assets/image/design-p-2.png">
      </div>
    </div>
  </div>
</template>

<style lang="scss">
#rightSide {
  width: calc((100vw/10)*2);
  height: 100vh;
  background: none;
  position: fixed;
  right: 0;
  .rightSide-wrap {
    .rightSide-content {
      position: absolute;
      bottom: 60px;
      right: 20px;
      img {
        height: 56vh;
      }
    }
  }
}
</style>

<script>
export default {
  name: 'rightSide'
}
</script>
