<script setup lang='ts'>
import { RouterView } from 'vue-router'
import NavBar from '@/components/NavBar.vue'</script>

<template>
  <v-app>
    <nav-bar />
    <v-main>
      <RouterView />
    </v-main>
  </v-app>
</template>

<style scoped>
</style>
