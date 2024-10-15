<template>
  <div class="mainContainer">
    <div class="secondaryContainer">
      <h1 class="pb-10" style="font-size: 70px;">Under Construction</h1>
      <v-icon
        class="pb-10"
        size="150px"
      >
        mdi-hammer-wrench
      </v-icon>
      <h2 style="color: grey;">I have older projects, but I would like to fill this out with new projects that actually show off my skill set</h2>
    </div>
  </div>
</template>
<script lang="ts">
export default {

}
</script>
<style scoped lang="scss">
.mainContainer {
  height: 100%; 
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.secondaryContainer {
  height: fit-content;
  width: fit-content;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}
</style>