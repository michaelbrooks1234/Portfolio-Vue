<template>
  <div class="mainContainer">
    <div class="titleContainer">
      <h1 class="titleText">
        Michael Brooks
      </h1>  
      <h3 class="subTitleText">Full Stack Engineer</h3>
    </div>
    <div class="extrasContainer">
      <span
        @click="$router.push('/experience')"
      >
        Experience
        <v-tooltip
          activator="parent"
          location="top"
        >
          <h3>A recap of my work experience up until this point</h3>
        </v-tooltip>
      </span>
      <span
        @click="$router.push('/projects')"
      >
        Projects
        <v-tooltip
          activator="parent"
          location="top"
        >
          <h3>Personal projects I have completed or are in progress</h3>
        </v-tooltip>
      </span>
      <span
        @click="$router.push('/contact')"
      >
        Contact
        <v-tooltip
          activator="parent"
          location="top"
        >
          <h3>Contact me!</h3>
        </v-tooltip>
      </span>
    </div>
  </div>
</template>

<script lang="ts">
  export default {
    data() {
      return {
        title: 'Michael Brooks',
        subTitle: 'Full Stack Engineer',
      }
    },
  }
</script>
<style scoped lang="scss">
@import '../styles/settings.scss';

.extrasContainer {
  font-size: 30px;
  width: 80%;
  display: flex;
  justify-content: space-between;
}

.extrasContainer > span {
  width: fit-content;
  cursor: pointer;
  user-select: none;
}

.extrasContainer > span:hover {
  color: $primary-color;
}

.mainContainer {
  margin-top: 20vh;
  height: 65vh;
  width: 100vw;
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-direction: column;
}

.subTitleText {
  font-size: 50px;
  color: grey;
  cursor: default;
}

.titleContainer {
  width: fit-content;
  text-align: center;
}

.titleText {
  font-size: 100px;
  user-select: none;
  cursor: default;
}

@media only screen and (max-width: 760px) {
  .extrasContainer {
    font-size: 20px;
  }

  .subTitleText {
    font-size: 30px;
    text-wrap: nowrap;
    color: grey;
  }

  .titleText {
    font-size: 70px;
  }
}
</style>