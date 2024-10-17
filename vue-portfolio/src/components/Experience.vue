<template>
  <v-container class="topContainer">
    <div class="titleContainer">
      <h1>Experience</h1><br>
      <h3 class="subtitle">Where have I been, what have I been doing??</h3>
    </div>
    <div class="contentContainer mt-6">
      <v-carousel
        style="height: fit-content;"
        :show-arrows="isMobile ? false : 'hover'"
      >
        <v-carousel-item
          v-for="(item, i) in experienceItems"
          :key="i"
        >
          <v-card
            class="ma-auto fill-height"
            :subtitle="item.subTitle"
            :title="item.title"
          >
            <template
              v-slot:prepend
            >
              <v-img
                :src="item.imgSrc"
                rounded
                width="40px"
              ></v-img>
            </template>
            <template>

            </template>
            <v-card-text
              class="bg-surface-light fill-height descriptionText pb-15"
              :class="isMobile ? 'pa-4' : 'pa-8'"
            >
              {{ item.description }}
              <br>
              <br>
              Skills Used: {{ item.skills }}
            </v-card-text>
          </v-card> 
        </v-carousel-item>
      </v-carousel> 
    </div>
  </v-container>
</template>

<script lang="ts">
export default {
  data() {
    return {
      experienceItems: [
        {
          imgSrc: 'https://media.licdn.com/dms/image/v2/C560BAQE6SQ2uwWXguA/company-logo_100_100/company-logo_100_100/0/1630645569166/sekady_logo?e=1736985600&v=beta&t=mhSMGtCr-N-LIZuPMfz9MBil93200ceuOyBQB57etAM',
          title: 'Software Developer', 
          subTitle: 'Sekady, Oct 2022 - Jul 2024',
          description: 'During my time with Sekady, I was a full stack developer that had worked on every part of their main platform. I did work on both the front end (Vue.js, Vuetify) and the back end (Node.js, Express.js, MongoDB), but also handled the automated testing done for these features as well by utilizing Cypress on the front end, and Mocha & Chai on the backend. I handled code reviews, helped solve technical and workflow problems, and did a lot of coding. The focus was about 50/50 front end to back end.',
          skills: 'Vue, Vuetify, MongoDB, Express.js, Mocha & Chai, Cypress, AWS, Git, Node.js'

        },
        {
          imgSrc: 'https://media.licdn.com/dms/image/v2/C4E0BAQFAIfHA00B5FA/company-logo_100_100/company-logo_100_100/0/1669114983739/chili_publish_logo?e=1736985600&v=beta&t=jyWKDmC5EQ09BCmadsJ6nTDipSv11fqvEoQ4Oi0IDzs',
          title: 'Client Success Engineer', 
          subTitle: 'Chili publish, Dec 2021 - Sep 2022',
          description: 'While I was a Client Success Engineer with CHILI publish I was providing support for our SaaS product. I was an API focused support member and would mainly help developers use our API to integrate our product. We used Node.js to make many example calls to the API as well work through the issue in meetings. We also created example integrations for our clients by utilizing html, css, and JavaScript. We would then package these example projects with electron and send them to the client. I also managed and migrated user data through Azure when necessary.',
          skills: 'JavaScript, TypeScript, Node.js, Electron, APIs, Customer Support'
        },
        {
          imgSrc: 'https://media.licdn.com/dms/image/v2/C560BAQHlV7bnFVNRmA/company-logo_100_100/company-logo_100_100/0/1677682249857/sykes_logo?e=1736985600&v=beta&t=0n5ryVFFmXjgClIfgN3JcaEN6qnVobQ_D5SxAz_U5H4',
          title: 'Technical Support Engineer', 
          subTitle: 'SYKES, Apr 2021 - Dec 2021',
          description: `At Sykes as a Technical Support Engineer I was helping out faculty in the public education sector with utilizing a book platform. Just a lot of customer service basically. This was one of my transitory roles that I had taken to get a step further into the Tech field on my journey to becoming a Software Engineer. I have learned a lot from this position as I have the rest but there isn't much to mention when it comes to my current focus.`,
          skills: 'Customer Service, Technical Problem Solving'
        },
      ],
    }
  },
  methods: {
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
.titleContainer {
  width: 100%;
  text-align: center; 
  position: absolute;
  top: 10%;
  right: 0;
}

.topContainer {
  display: flex;
  flex-direction: column;
  justify-content: center;
  height: 100%;
}

.contentContainer {
  height: fit-content;
}

.descriptionText {
  font-size: 22px;
}

.subtitle {
  color: grey;
}

@media only screen and (max-width: 700px) {
  .titleContainer {
    top: 5%;
  }
  .subtitle {
    display: none;
  }
}
</style>