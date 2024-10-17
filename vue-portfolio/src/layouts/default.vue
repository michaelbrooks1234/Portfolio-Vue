<template>
  <v-app>
    <NavBar />
    <v-main style="z-index: 2;">
      <router-view />
    </v-main>
    <Background style="z-index: 0;" />
    <AppFooter />
  </v-app>
</template>

<script setup lang="ts">
</script>