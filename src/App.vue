<template>
  <v-app>
    <v-toolbar density="compact">
      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-toolbar-title>
        <RouterLink to="/">Vuetify
        </RouterLink>
      </v-toolbar-title>

      <v-spacer></v-spacer>

      <v-menu transition="scale-transition">
      <template v-slot:activator="{ props }">
        <v-btn icon v-bind="props">
          <v-badge content="6" size="x-small" color="red-darken-2">
            <v-icon icon="mdi-bell" color="blue-darken-4"></v-icon>
          </v-badge>
        </v-btn>
      </template>
      <v-list>
        <v-list-item
          v-for="(notification, index) in notifications"
          :key="index"
          :value="index"
        >
          <v-list-item-title>
            <v-icon :color="notification.color" :icon="notification.icon"></v-icon>
            {{ notification.title }}
          </v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu>
      <v-btn to="/login" variant="outlined" size="small" color="red">
        Login
      </v-btn>
    </v-toolbar>
    
    <v-main>
      <v-fade-transition>
        <RouterView />
      </v-fade-transition>
    </v-main>
  </v-app>
</template>

<script setup lang="ts">
  import { RouterView } from 'vue-router'

  const notifications = [
  {
    title: "Message from A",
    icon: "mdi-email",
    color: "blue",
  },
  {
    title: "Message from B",
    icon: "mdi-email",
    color: "green",
  },
  {
    title: "Message from C",
    icon: "mdi-email",
    color: "red",
  },
  {
    title: "Message from D",
    icon: "mdi-email",
    color: "yellow",
  },
  {
    title: "Message from E",
    icon: "mdi-email",
    color: "purple",
  },
  {
    title: "Message from F",
    icon: "mdi-email",
    color: "orange",
  },
];
</script>