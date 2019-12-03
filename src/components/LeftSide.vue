<template>
  <div id="leftSide">
    <div class="leftSide-wrap">
      <div class="leftSide-content">
        <img src="../assets/image/design-p-1.png">
      </div>
    </div>
  </div>
</template>

<style lang="scss">
#leftSide {
  width: calc((100vw/10)*2);
  height: 100vh;
  background: none;
  position: fixed;
  left: 0;
  .leftSide-wrap {
    .leftSide-content {
      position: absolute;
      bottom: 50px;
      left: 20px;
      img {
        height: 60vh;
      }
    }
  }
}
</style>

<script>
export default {
  name: 'leftSide'
}
</script>
