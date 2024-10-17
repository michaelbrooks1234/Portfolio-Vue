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
    <!-- <div class="titleContainer">
      <h1>Projects</h1>
    </div>
    <div class="projectsContainer">
      <v-card
        v-for="(card, i) in cards"
        class="ma-4"
        width="344px"
        height="400"
        :key="i"
      >
        <v-img
          width="344px"
          :src="card.img"
          cover
        >
        </v-img>
        <v-card-title>
          {{ card.title }}
        </v-card-title>
        <v-card-subtitle>
          {{ card.subtitle }}
        </v-card-subtitle>
        <v-card-text>
          {{ card.text }}
        </v-card-text>
      </v-card>
    </div> -->
  </div>
</template>
<script lang="ts">
export default {
  data() {
    return {
      cards: [
        {
          img: '',
          title: 'Portfolio',
          subtitle: 'Vue, Vuetify, TypeScript',
          text : 'This is a project that does super cool things.. this is why it is cool!! blah blah blah blah blah blah blah. These are the technologies I used.... Blah blah blah blah blah. I hope you enjoyed me ted talk'
        },
        {
          img: '',
          title: 'Portfolio',
          subtitle: 'Vue, Vuetify, TypeScript',
          text : 'This is a project that does super cool things.. this is why it is cool!! blah blah blah blah blah blah blah. These are the technologies I used.... Blah blah blah blah blah. I hope you enjoyed me ted talk'
        },
        {
          img: '',
          title: 'Portfolio',
          subtitle: 'Vue, Vuetify, TypeScript',
          text : 'This is a project that does super cool things.. this is why it is cool!! blah blah blah blah blah blah blah. These are the technologies I used.... Blah blah blah blah blah. I hope you enjoyed me ted talk'
        },
        {
          img: '',
          title: 'Portfolio',
          subtitle: 'Vue, Vuetify, TypeScript',
          text : 'This is a project that does super cool things.. this is why it is cool!! blah blah blah blah blah blah blah. These are the technologies I used.... Blah blah blah blah blah. I hope you enjoyed me ted talk'
        },
      ],
    }
  }
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

.projectsContainer {
  height: 75vh;
  display: flex;
  flex-wrap: wrap;
  flex-direction: row;
  width: 80vw;
  justify-content: space-evenly;
  align-content: flex-start;
  overflow: auto;
}

.secondaryContainer {
  height: fit-content;
  width: fit-content;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}

.titleContainer {
  width: 100%;
  text-align: center; 
  position: absolute;
  top: 5%;
  right: 0;
}
</style>