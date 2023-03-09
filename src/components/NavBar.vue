<template>
  <v-app-bar>
    <v-app-bar-title>E-commerce</v-app-bar-title>


    <v-app-bar-nav-icon
      @click.stop='drawer = !drawer'
    >
      <v-icon :icon='navIcon'></v-icon>
    </v-app-bar-nav-icon>
  </v-app-bar>
  <v-navigation-drawer
    v-model='drawer'>
    <ul v-for='{name} in navItems'>
      <li>{{ name }}</li>
    </ul>
  </v-navigation-drawer>
</template>

<script lang='ts'>
import { ref } from 'vue'

export default {
  name: 'NavBar',
  setup() {
    const drawer = ref<boolean>(false)
    const navItems: object[] = [
      {
        name: 'Homepage'
      },
      {
        name: 'About us'
      },
      {
        name: 'Products'
      }
    ]
    const navIcon = drawer.value ? 'mdi-close' : 'mdi-menu'

    return {
      drawer,
      navItems,
      navIcon
    }
  }
}
</script>

<style lang='scss' scoped>
.v-app-bar {
  padding: 10px;

  .v-app-bar-title {
    margin: 14px;
    font-size: 22px;
    font-family: 'Lobster', cursive;
    text-transform: uppercase;
  }
}

.v-navigation-drawer {
  height: 100vh !important;
  width: 100% !important;

  ul {
    display: grid;
    place-items: center;
  }

  li {
    color: black;
  }
}
</style>