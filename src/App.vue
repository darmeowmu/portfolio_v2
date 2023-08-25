<template>
  <v-app :theme="darkMode ? 'dark' : ''">
    <v-app-bar scroll-behavior="elevate">
      <v-container id="nav-container">

        <v-app-bar-title>
          <div class="d-flex align-center justify-space-between">
            <v-btn @click="scrollToTop" :ripple="false"><span class="font-weight-bold">DARWIN FAGARANG</span></v-btn>

            <v-app-bar-nav-icon v-if="mobile" variant="text" @click="drawer = !drawer"></v-app-bar-nav-icon>
            <div v-else>
              <Nav :dark-theme="darkMode" @themeToggle="darkMode = !darkMode" class="d-flex text-button" />
            </div>
          </div>
        </v-app-bar-title>
      </v-container>
    </v-app-bar>
    <v-navigation-drawer v-if="mobile" v-model="drawer" location="right" class="text-center">
      <Nav :dark-theme="darkMode" @themeToggle="darkMode = !darkMode" />
    </v-navigation-drawer>

    <v-main id="main">
      <RouterView />
    </v-main>

    <v-footer id="footer" class=" text-center d-flex flex-column" theme="dark">
      <div class="pb-1">
        <v-btn v-for="icon in icons" :key="icon" class="mx-4" :icon="icon" variant="text"></v-btn>
      </div>
      <h5>Built by Win Fagarang</h5>
    </v-footer>
  </v-app>
</template>

<script setup lang="ts">
import Nav from './components/Nav-list.vue'
import { provide } from 'vue';
import { ref } from 'vue';
import { RouterView } from 'vue-router'
import { useDisplay } from 'vuetify';

const { mobile } = useDisplay();
const drawer = ref(false);

const icons = ['mdi-linkedin', 'mdi-github']

function scrollToTop() {
  window.scrollTo({
    top: 0,
  });
  if (window.location.hash) {
    history.replaceState(null, '', window.location.pathname + window.location.search);
  }
}

const darkMode = ref(false)

provide('useMobile', mobile);

</script>

<style scoped>
#main {
  width: 1000px;
  margin: 0 auto;
}

#nav-container {
  width: 1050px;
  ;
}
</style>
