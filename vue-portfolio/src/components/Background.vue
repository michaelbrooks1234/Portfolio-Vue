<template>
  <div class="mainContainer">
    <div class="bottomLeftCorner"></div>
    <div class="topRightCorner"></div>
    <div class="bottomRightCorner"></div>
    <div class="centerBottomLine"></div>
    <div class="centerTopLine"></div>
    <div class="centerRightLine"></div>
    <div class="centerLeftLine"></div>
  </div>
</template>
<script setup lang="ts">
</script>
<style lang="scss" scoped>
@import '../styles/settings.scss';

.mainContainer {
  position: fixed;
  top: 0;
  left: 0;
  height: 100vh;
  width: 100vw;
  user-select: none;
}

.bottomLeftCorner {
  position: absolute;
  height: 250px;
  width: 150px;
  bottom: 0;
  margin: 0 0 60px 30px;
  border-bottom: solid 2px $primary-color;
  border-left: solid 2px $primary-color;
}

.bottomRightCorner {
  position: absolute;
  height: 250px;
  width: 150px;
  bottom: 0;
  right: 0;
  margin: 0 40px 60px 0;
  border-bottom: solid 2px $primary-color;
  border-right: solid 2px $primary-color;
}

.centerBottomLine {
  position: absolute;
  right: 25%;
  width: 50vw;
  bottom: 0;
  margin-bottom: 60px;
  border-bottom: dotted 2px $primary-color;
}

.centerRightLine {
  position: absolute;
  top: 34vh;
  height: 30vh;
  right: 0;
  margin-right: 40px;
  border-right: solid 2px $primary-color;
}

.centerLeftLine {
  position: absolute;
  top: 34vh;
  height: 30vh;
  left: 0;
  margin-left: 30px;
  border-left: solid 2px $primary-color;
}

.centerTopLine {
  position: absolute;
  right: 25%;
  width: 50vw;
  margin-top: 30px;
  border-bottom: dotted 2px $primary-color;
}

.topRightCorner {
  position: absolute;
  top: 0;
  right: 0;
  height: 250px;
  width: 150px;
  margin: 30px 40px 0 0;
  border-top: solid 2px $primary-color;
  border-right: solid 2px $primary-color;
}

@media only screen and (max-width: 700px) {
  .mainContainer {
    display: none;
  }
}
 
</style>