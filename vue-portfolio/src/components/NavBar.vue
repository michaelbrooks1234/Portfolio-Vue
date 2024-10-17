<template>
    <v-container class="ma-0 pa-0">
      <v-btn 
        elevation="0"
        @click="drawer = true"
        base-color="background"
        icon="mdi-menu"
        class="pa-4 ma-4"
        style="z-index: 12;"
      />  
      <v-navigation-drawer
        v-model="drawer"
        temporary
      >
        <div class="avatarPic py-12">
          <v-avatar
            size="80px"
          >
            <v-img
              alt="Michael"
              src="https://media.licdn.com/dms/image/v2/D5603AQEMXJclBwBM2Q/profile-displayphoto-shrink_800_800/profile-displayphoto-shrink_800_800/0/1698597923442?e=1734566400&v=beta&t=684ZjpbnkAurCofrtwXChuf_0c7f0gQ11nUn5ajCDJM"
            ></v-img>
          </v-avatar>
          <v-list-item
            class="text-secondary"
            title="Michael Brooks"
            subtitle="Software Engineer"
          >
          </v-list-item>
        </div>
        <v-list
          nav
        >
          <v-list-item
            v-for="(item, i) in items"
            :key="i"
            :prepend-icon="item.icon"
            @click="$router.push(item.route), drawer = false"
            class="navItem"
          >  
            {{ item.title }}
          </v-list-item>
        </v-list>
        <div>
          <v-img
             
          ></v-img>
          <v-img

          ></v-img>
        </div>
      </v-navigation-drawer>
    </v-container>
</template>
<script lang="ts">
export default {
  data() {
    return {
      drawer: false,
      items: [
        {
          title: 'Home',
          icon: 'mdi-home',
          route: '/'
        },
        {
          title: 'Experience',
          icon: 'mdi-briefcase',
          route: '/experience'
        },
        {
          title: 'Projects',
          icon: 'mdi-account-hard-hat',
          route: '/projects'
        },
        {
          title: 'Contact Me',
          icon: 'mdi-send',
          route: '/contact'
        },
      ]
    }
  },
}
</script>
<style lang="scss" scoped>
@import '../styles/settings.scss';
.hidden {
  display: none;
}
.avatarPic {
  width: 100%;
  display: flex;
  justify-content: center;
}
.navItem:hover {
  background-color: $primary-color;
}
</style>