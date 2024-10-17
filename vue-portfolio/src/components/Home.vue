<template>
  <div class="mainContainer">
    <div style="display: flex; align-items: center;">
      <v-avatar
        size="180px" 
        class="ma-5 avatar"
      >
        <v-img
          alt="Michael"
          src="https://media.licdn.com/dms/image/v2/D5603AQEMXJclBwBM2Q/profile-displayphoto-shrink_800_800/profile-displayphoto-shrink_800_800/0/1698597923442?e=1734566400&v=beta&t=684ZjpbnkAurCofrtwXChuf_0c7f0gQ11nUn5ajCDJM"
        ></v-img>
      </v-avatar>
      <div class="titleContainer">
        <h1 class="titleText">
          Michael Brooks
        </h1>  
        <h3 class="subTitleText">Full Stack Engineer</h3>
      </div>
    </div>
    <div class="extrasContainer">
      <span
        @click="$router.push('/experience')"
      >
        Experience
        <v-tooltip
          v-if="!isMobile"
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
          v-if="!isMobile"
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
          v-if="!isMobile"
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
  computed: {
    isMobile() {
      if(/Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent)) {
        return true
      } else {
        return false
      }
    },
  }
}
</script>
<style scoped lang="scss">
@import '../styles/settings.scss';

.extrasContainer {
  font-size: 30px;
  width: 80%;
  display: flex;
  margin-bottom: 10px;
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
  margin-top: 25vh;
  height: 60vh;
  width: 100vw;
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-direction: column;
}

.subTitleText {
  font-size: 50px;
  text-align: start;
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

@media only screen and (max-width: 906px) {
  .avatar {
    display: none;
  }

  .subTitleText {
    text-align: center;
  }
}


</style>