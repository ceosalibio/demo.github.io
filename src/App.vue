<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
    <v-app-bar-nav-icon @click="navDrawer = !navDrawer"></v-app-bar-nav-icon>
    </v-app-bar>
    <v-navigation-drawer v-model="navDrawer" app>
      <v-list>
        <v-list-item v-for="(item, index) in navList" :key="index" :to="item.to">
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-title> {{ item.title }} </v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  data: () => ({
    navDrawer: false,
    navList: [
      { title: "Home", icon: "mdi-home", to: "/" },
      { title: "About", icon: "mdi-information", to: "/About" },
      { title: "V-Hooks", icon: "mdi-format-list-bulleted", to: "/vhooks" },
    ],
  }),
};
</script>
