<script setup>
  import {ref} from "vue";

  const showDrawer = ref(false);

</script>

<template>
  <v-layout class="rounded rounded-md">
    <v-navigation-drawer temporary v-model="showDrawer">
      <v-list>
        <v-list-item title="Navigation drawer"></v-list-item>
      </v-list>
      <v-list
          :items="items"
          item-title="name"
          item-value="id"
      ></v-list>
    </v-navigation-drawer>

    <v-app-bar color="primary">
      <template v-slot:prepend>
        <v-app-bar-nav-icon @click="showDrawer = !showDrawer"></v-app-bar-nav-icon>
      </template>

      <v-app-bar-title>Ромашка</v-app-bar-title>

      <v-spacer></v-spacer>

      <template v-slot:append class="hidden-sm-and-down">
        <v-btn height="100%" flat>Link 1</v-btn>
      </template>
    </v-app-bar>

    <v-main class="d-flex align-center justify-center">
      <router-view></router-view>
    </v-main>
  </v-layout>
</template>

<style scoped>

</style>
