<template>
  <v-app :theme="darkMode ? 'dark' : ''">
    <v-app-bar scroll-behavior="elevate">
      <v-container>
        <v-app-bar-title class="pl-0">
          <div class="d-flex align-center justify-space-around">
            <v-btn @click="scrollToTop"><span class="font-weight-bold">DARWIN FAGARANG</span></v-btn>
            <div>
              <v-btn icon @click="darkMode = !darkMode"><v-icon :icon="darkMode ? 'mdi-white-balance-sunny' : 'mdi-moon-waxing-crescent'"></v-icon></v-btn>
              <v-btn variant="text" href="#projects"> <span class="font-weight-medium">Projects</span> </v-btn>
              <v-btn variant="text" href="#about"> <span class="font-weight-medium">About</span> </v-btn>
              <v-btn variant="text" @click="dialog = true"><span class="font-weight-medium">Contact
                  <v-dialog transition="dialog-top-transition" v-model="dialog" activator="parent" width="auto">
                    <Modal @close-dialog="dialog=false" />
                  </v-dialog>
                </span>
              </v-btn>
              <v-btn variant="text" href="https://drive.google.com/file/d/1swsfTa6Pyxiah85AqOw5Ut6KrXXSlIqW/view"><span
                  class="font-weight-medium">Resume</span><v-icon icon="mdi-arrow-top-right-bold-box-outline"></v-icon>
              </v-btn>
            </div>
          </div>
        </v-app-bar-title>
      </v-container>
    </v-app-bar>

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
import { ref } from 'vue';
import { RouterView } from 'vue-router'
import Modal from './components/Modal.vue'

const icons = ['mdi-linkedin', 'mdi-github']

function scrollToTop() {
  window.scrollTo({
    top: 0,
  });
  if (window.location.hash) {
    history.replaceState(null, '', window.location.pathname + window.location.search);
  }
}

const dialog = ref(false)
const darkMode = ref(false)
</script>

<style scoped>
#main {
  width: 1110px;
  margin: 0 auto;
}

</style>
